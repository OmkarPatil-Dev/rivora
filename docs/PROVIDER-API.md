# Rivora Provider API v1

Rivora starts with no providers and no media. It installs JSON manifests, not executable extensions or APKs. Cloudstream and Mihon extensions are not compatible. Providers run their own API outside the app.

## Manifest

Publish an HTTPS JSON file (maximum 64 KiB), for example `https://your-domain.com/rivora.json`:

```json
{
  "format": "rivora",
  "apiVersion": 1,
  "id": "com.your-domain.library",
  "name": "My Personal Library",
  "version": "1.0.0",
  "description": "Videos I own and am entitled to share.",
  "website": "https://your-domain.com/",
  "apiBase": "https://your-domain.com/api/v1/",
  "mediaOrigins": ["https://media.your-domain.com"],
  "artworkOrigins": ["https://images.your-domain.com"]
}
```

Use a stable reverse-domain ID and numeric `major.minor.patch` version. Names are limited to 80 characters, descriptions to 1,000. Origin permissions are exact HTTPS origins (up to 32 of each), without paths, wildcards, credentials or nonstandard ports. Include every HLS playlist, segment and encryption-key origin. Unlisted artwork and media are rejected. Public DNS hostnames are required; local/private-IP URLs and custom ports are not supported in v1. All URLs must point directly to their resources; JSON and HLS fetches reject redirects.

Rivora fetches the manifest, shows its publisher and permissions for review, then stores it only when the user selects **Add and use**. Reviewing the same ID replaces its configuration. Removal stops using that provider; its local saved titles and history remain for a future reinstall. Provider ID plus API base isolate library data, so changing the API base starts a separate library.

## Server requirements

- HTTPS with a valid certificate. Return `application/json` for API responses.
- Enable CORS on the manifest, API, artwork, playlists, keys, and media segments. For an anonymous public API use `Access-Control-Allow-Origin: *`; no cookies or credentials are sent by JSON or HLS fetches.
- For restricted CORS allow `https://appassets.androidplatform.net` and your deployed web origin. Local preview origin: `http://127.0.0.1:5174`.
- Support GET and byte ranges for media. If OPTIONS is needed, allow GET, HEAD, OPTIONS and Range; expose Content-Length, Content-Range and Accept-Ranges.
- API responses must be below 4 MB and respond within 20 seconds. HTTP errors become provider errors, not empty successful results.
- v1 does not support custom authorization headers, login flows, DRM, HTML scraping, executable plugins or subtitle-file sidecars. Private servers can issue short-lived signed HTTPS media URLs from a suitably secured deployment, but v1 itself has no account/token UI.
- Providers must distribute only content they have the right to supply. Rivora does not bypass access controls.

## Shared types

Title/category IDs are positive safe integers, stable within a provider. Each season, movie or special has a distinct title ID. Episode IDs are provider-global unique strings of 1–120 ASCII letters, digits, underscores or hyphens. Episode numbers are positive numbers.

```json
{"id":1,"title":"My Film","poster":"https://images.your-domain.com/film.jpg"}
```

A detail record:

```json
{
  "id":1,"title":"My Film","poster":"https://images.your-domain.com/film.jpg",
  "type":"Movie","overview":"A personal film.","genres":"Documentary",
  "runtime":"12 min","premiered":"2026","score":"","age":"PG",
  "status":"Completed","relations":[],"similar":[]
}
```

`type` can be TV, Movie, OVA, Special. `relations` entries are `{ "id":2, "rel":"Sequel", "poster":"..." }`. Supported relation labels include Prequel, Sequel, Side Story, Parent Story, Spin-off, Summary and Full Story. Use reciprocal links where relevant. `similar` is an array of title cards. Plain text only; HTML is rendered as text. Missing optional descriptive strings display as empty strings. `age: "Rx"` or genres containing Hentai/ Erotica are filtered unless the viewer opts in; spotlight filtering is stricter.

## Routes relative to apiBase

| GET route | JSON response |
| --- | --- |
| `home` | `{ "featured": <detail or null>, "sections": [{"name":"My Library","posts":[<card>]}] }` |
| `post?id=1` | One detail record; its ID must match the request |
| `search?query=film&page=1` | `{ "posts": [<card>] }` |
| `latest?page=1` | `{ "posts": [<card>] }` |
| `categories` | `{ "categories": [{"id":1,"name":"Documentary"}] }` |
| `category?id=1&page=1` | `{ "posts": [<card>] }` |
| `titles/1/episodes` | `{ "episodes": [{"id":"film-1","number":1,"name":"My Film","filler":false}] }` |
| `episodes/film-1/audio` | `{ "audio": ["sub", "dub"] }` |
| `episodes/film-1/stream?audio=sub` | `{ "url":"https://media.your-domain.com/master.m3u8", "type":"hls" }` |

Pages begin at 1. Return an empty posts array when there are no more results. Unknown IDs should return 404. Include all episodes for a title in its episode response. A movie is a title with one episode. No scraping or old application response format is implied by these routes.

`sub` and `dub` are the player's two variants. Only advertise variants actually available. `sub` must include the provider's intended subtitles in the video or compatible HLS stream; Rivora does not synthesize subtitles. Return 404 for an unavailable variant. `type` is `hls` or `mp4`; direct MP4 uses the browser video element. HLS is fetched with hls.js, including variant playlists, AES keys and segments, and every requested origin is checked. DRM is unsupported.

## Verification checklist for provider authors

1. Fetch the manifest and each JSON route with the app's Origin header and verify CORS.
2. Review/install the manifest through Settings → Extensions.
3. Verify Home, Search, a detail page, season selection and a playable episode.
4. Switch Sub/Dub and ensure the audio response matches available variants.
5. Check all CDN origins, HLS relative paths, byte-range responses, signed-link expiry and expired-link errors.
6. Switch to a second provider with the same numeric title IDs and verify history does not mix.

No providers or extension directories are shipped or endorsed by default. The test suite uses intercepted synthetic provider responses; its fixtures are not public content sources.

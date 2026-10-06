# Privacy notice

_Last updated: 6 October 2026 · Applies to Rivora 1.0.0 (`com.thecodestorm.rivora`)_

Rivora is designed to keep your library on your device. This page explains, in plain language, what stays local and what leaves your phone or TV.

## Stays on your device

- Installed extensions and their settings
- My List, watch progress and Continue Watching
- Downloaded videos
- App preferences (player, updates, app lock)

These are never sent to Rivora's service.

## Sent to Rivora's service

When the app starts, roughly once a minute while it is open, and when it is paused or resumed, Rivora checks in with its administration service. A check-in contains:

| Data | Why |
| :--- | :--- |
| A hashed, app-specific device identifier and a random installation ID | Tell installations apart without using your name or account |
| Device model, manufacturer, Android version, app version, phone/TV type | Compatibility and support |
| Foreground session ID and duration | Basic usage statistics |
| Approximate location, derived by the server from your connection (not GPS) | Regional statistics |

The service **does not** receive your extensions, watch history, search terms or media links. The service can disable app access for a device or for all devices; a disabled device stays disabled while offline.

## Sent to others

- **Extension providers** you add receive requests for their catalogues, artwork and streams, like any website you visit. Their own privacy policies apply.
- **GitHub** receives a request when Rivora checks for updates in this repository.
- **Telegram** opens only if you tap a community link.

## Your choices

- Uninstall Rivora or clear its data to remove everything stored locally. A reinstall creates a new installation ID.
- Remove any extension at any time in **Settings → Extensions**.
- Questions or removal requests: ask in the [Rivora support chat](https://t.me/RivoraAppChatroom).

Rivora is not directed at children.

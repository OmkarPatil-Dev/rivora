<p align="center">
  <img src="assets/banner.png" alt="Rivora - Your local library. Your player." width="100%" />
</p>

<p align="center">
  <a href="https://github.com/OmkarPatil-Dev/rivora/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/OmkarPatil-Dev/rivora?style=for-the-badge&logo=github&label=Release&color=1f6dff" /></a>
  <a href="https://github.com/OmkarPatil-Dev/rivora/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/OmkarPatil-Dev/rivora/total?style=for-the-badge&label=Downloads&color=4aa8ff" /></a>
  <img alt="Android 8.0+" src="https://img.shields.io/badge/Android-8.0%2B-3DDC84?style=for-the-badge&logo=android&logoColor=white" />
  <img alt="Phone and TV" src="https://img.shields.io/badge/Phone_%26_TV-ready-0b2a5c?style=for-the-badge" />
</p>

<p align="center">
  <a href="https://github.com/OmkarPatil-Dev/rivora/releases/latest">
    <img alt="Download the latest APK" src="https://img.shields.io/badge/⬇_Download_APK-Latest_release-1f6dff?style=for-the-badge&labelColor=0b1730" height="46" />
  </a>
</p>

<p align="center">
  <a href="https://t.me/RivoraApp"><img alt="Telegram channel" src="https://img.shields.io/badge/Telegram-Channel-26A5E4?style=flat-square&logo=telegram&logoColor=white" /></a>
  <a href="https://t.me/RivoraAppChatroom"><img alt="Telegram support chat" src="https://img.shields.io/badge/Telegram-Support_chat-26A5E4?style=flat-square&logo=telegram&logoColor=white" /></a>
  <img alt="Closed source" src="https://img.shields.io/badge/source-closed-555?style=flat-square" />
</p>

<p align="center">
  <a href="#-about">About</a> •
  <a href="#-screenshots">Screenshots</a> •
  <a href="#-features">Features</a> •
  <a href="#-install">Install</a> •
  <a href="#legal">Legal & Compliance</a> •
  <a href="#-community--support">Support</a>
</p>

---

## ✨ About

**Rivora** is an advanced, strictly neutral **Bring Your Own Content (BYOC)** media player and JSON metadata viewer for Android devices and Android TV. It is designed to act as a frontend interface for your personal media servers, public domain archives, and custom REST API endpoints.

**Rivora ships completely empty.** The application contains no built-in media, no pre-configured servers, no scraping scripts, and no copyrighted material. You provide the endpoints (Rivora JSON manifests or compatible third-party HTTPS endpoints), and Rivora translates them into a beautiful, remote-friendly grid UI.

> [!NOTE]
> Rivora is **closed source**. This repository hosts the official APK releases, documentation, and the issue tracker.

## 📸 Screenshots

<table>
  <tr>
    <td align="center" width="25%"><img src="assets/screenshots/home.png" alt="Empty home tab showing no bundled content" /><br/><sub><b>Empty State UI</b></sub></td>
    <td align="center" width="25%"><img src="assets/screenshots/browse.png" alt="Built-in help menu" /><br/><sub><b>Help & Support</b></sub></td>
    <td align="center" width="25%"><img src="assets/screenshots/details.png" alt="Extensions menu for adding providers" /><br/><sub><b>Extension Manager</b></sub></td>
    <td align="center" width="25%"><img src="assets/screenshots/downloads.png" alt="Offline downloads tab" /><br/><sub><b>Local Cache</b></sub></td>
  </tr>
  <tr>
    <td align="center"><img src="assets/screenshots/search.png" alt="Empty search tab" /><br/><sub><b>No Built-In Media</b></sub></td>
    <td align="center"><img src="assets/screenshots/preview.png" alt="Empty list tab" /><br/><sub><b>Awaiting Providers</b></sub></td>
    <td align="center"><img src="assets/screenshots/settings.png" alt="App and player settings" /><br/><sub><b>Player Settings</b></sub></td>
    <td align="center"><img src="assets/screenshots/updates.png" alt="Update checker menu" /><br/><sub><b>Built-in Updates</b></sub></td>
  </tr>
</table>

<p align="center"><sub><b>Disclaimer:</b> Screenshots demonstrate the application's native empty-state interface. Rivora is an independent utility software and strictly ships with no pre-bundled media, content, or third-party extensions.</sub></p>

## 🚀 Features

<table>
  <tr>
    <td width="50%" valign="top">

### 🎬 Premium UI Organization
- Auto-rotating **metadata spotlight**
- Dynamic UI rows and **Watch History** tracking
- Rich metadata pages with folder/file parsing
- **My List** to bookmark your files
- Fast, aggregated search through your connected endpoints

</td>
    <td width="50%" valign="top">

### 🧩 Bring Your Own Content (BYOC)
- Support for **Rivora JSON manifests** and compatible third-party REST APIs
- Connect public domain archives, personal network attached storage (NAS), or legal third-party metadata APIs
- Strict permissions: review every endpoint before it connects
- Separate history and metadata isolated per endpoint

</td>
  </tr>
  <tr>
    <td valign="top">

### ▶️ Advanced Video Player
- Gesture-driven UI: swipe left for **brightness**, right for **volume**
- **Hold for 2× speed**, double-tap to seek (5 / 10 / 30 s)
- Fit / Fill / Stretch, playback speed, touch lock
- **Sleep timer** and next-file autoplay countdown
- Seamless external player routing (e.g., VLC, MX Player)

</td>
    <td valign="top">

### 📥 Offline Caching
- Save **MP4** and **HLS** network streams for offline viewing
- Cached files remain completely local on your device storage
- Dedicated **Downloads** tab with gesture controls
- Optional unmetered-network safety toggles

</td>
  </tr>
  <tr>
    <td valign="top">

### 📺 Phone & TV Native
- Touch-first layout for mobile devices
- Deeply integrated D-pad/Remote layout for Android TV
- Immersive, pure dark-mode interface

</td>
    <td valign="top">

### 🔒 Privacy & Security
- **App lock** via biometrics or device PIN
- Recents thumbnails hidden while locked (Android 13+)
- Local-only history: no central database tracking your media
- **Opt-in updates:** checks this repo on your schedule, never installs silently

</td>
  </tr>
</table>

## 📲 Install

1. Go to **[Releases - Latest](https://github.com/OmkarPatil-Dev/rivora/releases/latest)**.
2. Under **Assets**, download the `rivora-x.y.z.apk` file.
3. Open the APK on your phone or TV. If Android asks, allow **Install unknown apps** for your browser or file manager.
4. Launch **Rivora** 🎉

| Requirement | |
| :--- | :--- |
| Android version | **8.0 (Oreo) or newer** |
| Devices | Phones, tablets and Android TV |
| Package name | `com.thecodestorm.rivora` |
| Architectures | ARM devices (arm64-v8a, armeabi-v7a) |

> [!TIP]
> To stay updated, open **Settings - Updates - Check now**. The app securely checks this exact repository for new signed releases and opens the page for you to review.

<a id="legal"></a>
## ⚖️ Legal & Compliance

**Rivora is strictly a neutral media player and metadata client.** 

- **No Content Hosted or Provided:** The developers of Rivora do not host, provide, archive, distribute, or scrape any media, copyrighted or otherwise. The app is a completely empty utility software.
- **Zero Affiliation with Add-ons:** The application supports standard JSON-based API manifests. The developer has absolutely no affiliation with, nor do they endorse, host, or monitor, any third-party add-ons, providers, or endpoints created by the community.
- **User Responsibility:** Users are strictly responsible for the endpoints they choose to connect to the application. Rivora explicitly condemns piracy and intellectual property infringement. 
- **Regulatory Compliance:** Rivora operates in strict compliance with the **Information Technology Act, 2000 (India)** (including Safe Harbor provisions under Section 79 as a neutral intermediary software), the **Copyright Act, 1957**, the **DMCA**, and the **Google Play Developer Distribution Agreement**. 

### 🛑 Anti-Infringement Policy & Grievance Contact
Rivora does not tolerate the use of its application for unauthorized access to copyrighted content. Since the app operates entirely client-side without central servers, the developer cannot moderate, block, or see the custom URLs a user inputs on their personal device. 

If you believe a third-party API or GitHub repository is distributing infringing JSON manifests, you must issue your takedown notice directly to the host of that specific server or repository. For application-specific legal inquiries or grievance reporting, please use our issue tracker or contact us via our official Telegram channel.

## ❓ FAQ

<details>
<summary><b>Does Rivora include movies, shows or subscriptions?</b></summary>
<br/>

**Absolutely not.** Rivora is purely a media player tool. It does not host, sell, bundle, or scrape any videos. What you view depends entirely on the public domain archives or personal server URLs you manually provide.
</details>

<details>
<summary><b>Why won't my video file play?</b></summary>
<br/>

Playback depends entirely on your connected source's container, codecs, and your device hardware. Try using the **Open in another app** feature to route the file to an external decoder like VLC or MX Player.
</details>

<details>
<summary><b>Is my data shared or tracked?</b></summary>
<br/>

No. Your endpoints, My List, and watch progress stay entirely on your local device storage. We do not track what media you play. Rivora only pings its own service for basic crash analytics. Read the full **[Privacy notice](PRIVACY.md)**.
</details>

## 💬 Community & Support

| | |
| :--- | :--- |
| 📢 **Announcements** | [t.me/RivoraApp](https://t.me/RivoraApp) |
| 💬 **Help & chat** | [t.me/RivoraAppChatroom](https://t.me/RivoraAppChatroom) |
| 🐞 **Bug reports** | [Open an issue](https://github.com/OmkarPatil-Dev/rivora/issues/new/choose) |
| 📝 **What's new** | [Changelog](CHANGELOG.md) |

When reporting a UI bug or crash, please include your **app version, device model, and Android version**. **Never** post private API endpoints, passwords, or tokens in the public chat.

---

<p align="center">
  <img src="assets/logo.png" width="72" alt="Rivora logo" />
</p> 
<p align="center">
  <b>Rivora</b> · Crafted with ♥ by <b>TheCodeStorm</b><br/>
  <sub>© 2026 TheCodeStorm. All rights reserved. Rivora is an independent media player and is not affiliated with, endorsed by, or sponsored by any streaming service or third-party API provider.</sub>
</p>

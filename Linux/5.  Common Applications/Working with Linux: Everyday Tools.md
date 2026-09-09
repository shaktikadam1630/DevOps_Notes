# Working with Linux: Everyday Tools

This module is a practical tour of the applications you'll actually use day to day on Linux — internet tools, office and development software, media playback and editing, and creative/graphics applications.

---

## 1. Internet Applications

Linux provides a full range of network-aware applications: web browsers, email clients, file transfer tools, and messaging/conferencing apps.

### Web Browsers

| Browser | Notes |
|---|---|
| **Firefox** | Default on many distros (Ubuntu, Fedora); open source, actively maintained, fully featured |
| **Google Chrome / Microsoft Edge** | Proprietary, `.deb`/`.rpm` packages, full ecosystem sync |
| **Chromium** | Open source foundation Chrome is built on — same core, no Google's proprietary additions |
| **GNOME Web (Epiphany)** | Lightweight, GNOME-integrated, minimal interface |
| **Opera** | Proprietary, built-in VPN and ad blocker |
| **Konqueror** | Browser + file manager integrated with KDE |

**Example:** A developer who wants Chrome's DevTools but not Google's telemetry often runs **Chromium** instead — same rendering engine, same debugging tools, without the proprietary layer on top.

### Email Applications

All Linux email clients use standard protocols: **IMAP** (messages stay on the server, synced across devices — the current standard), **POP3** (downloads messages locally, less common now), and **SMTP** for sending.

| Client | Type | Notes |
|---|---|---|
| **Thunderbird** | Graphical | Widely used, IMAP/POP3/OAuth2, calendar + tasks, large extension

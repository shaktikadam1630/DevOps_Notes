# System Settings

This module covers the **Settings** application — the central place to configure your system without touching the command line — and the additional tools (GNOME Tweaks, Extensions) that fill in what Settings intentionally leaves out.

---

## 1. Accessing System Settings

The **Settings** app is where you adjust displays, manage network connections, change the date and time, configure users, and much more.

![Navigating the Settings App](https://github.com/shaktikadam1630/DevOps_Notes/blob/main/Linux/images/settings-navigation-map.png?raw=true)

**Opening Settings on GNOME:**
- Click the icon cluster in the upper-right corner → select the **Settings** icon (usually a gear), or
- Search "Settings" in the Activities Overview

**Example:** On Ubuntu, Settings is also pinned to the sidebar dock by default — so it's often faster to just click its icon directly rather than searching for it.

> **Note:** The exact layout varies between distributions and GNOME versions, so a setting's location may differ slightly from what's described here. If you can't find something immediately, scan the sidebar — most things are where you'd intuitively expect them to be.

---

## 2. Navigating System Settings

The Settings sidebar organizes options into logical categories. Selecting a category opens its options in the main panel.

| Category | What's There |
|---|---|
| **Displays** | Screen resolution, refresh rate, multi-monitor configuration |
| **Network / Wi-Fi** | Wired and wireless connection management |
| **Date & Time** | Time zone, automatic time synchronization |
| **Users** | User accounts, passwords, login pictures |
| **Apps / Default Applications** | Which application handles each file type or task |

Some options nest one level deeper depending on your distribution. On older Ubuntu versions, for example, display settings live under **Devices → Displays** rather than directly under **Displays**. If a setting isn't where you expect, check for a sub-category first.

**Example — Configuring a User:** Click **Users** (may be nested under **System**) to set a user's login picture, password, and other attributes. Some fields may show "Some settings are locked" — click **Unlock** and authenticate to make changes, a safeguard against casual/accidental account edits.

**Example — App Permissions:** Under **Apps**, selecting an installed application (e.g., Firefox) shows granular permission toggles — notifications, running in background, microphone/audio access — similar in spirit to app permissions on a smartphone.

---

## 3. GNOME Tweaks and Extensions — Revisited for System Config

As covered earlier in this series, **GNOME Tweaks** and **GNOME Extensions** are the tools to reach for when Settings doesn't expose what you need. Several settings users reasonably expect to find in Settings — startup apps, fine-grained font rendering, advanced keyboard behavior — only live in these two tools.

### Startup Applications

To launch a specific app automatically at login, configure it in **GNOME Tweaks → Startup Applications**. While some individual apps offer their own "Start at Login" toggle, Tweaks remains the only reliable, universal method across distributions.

**Example:** Configuring a note-taking app to auto-launch every login means it's already open and ready the moment your desktop loads — no need to remember to open it manually each morning.

### Keyboard Layout and Behavior

This has shifted in recent GNOME versions:

| Setting Type | Where It Lives |
|---|---|
| Basic language layouts, key repeat | **Settings → Keyboard** (Ubuntu 24.04, Fedora 40+) |
| Advanced remapping (e.g., CapsLock → Ctrl or Escape) | **GNOME Tweaks → Keyboard & Mouse → Additional Layout Options** |

### Managing Extensions

On distributions running **GNOME 46+** (Ubuntu 24.04, Fedora 40+, RHEL 10, openSUSE Tumbleweed), extension management has moved entirely out of Tweaks and into the dedicated **Extensions** app.

- On **Fedora** and **openSUSE**, a popular alternative called **Extension Manager** is widely used — unlike the default Extensions app, it lets you browse and install extensions directly, without needing a browser connector to the GNOME Extensions website.

> **Compatibility note:** On cutting-edge distributions (Fedora 43/44, openSUSE Tumbleweed) running GNOME 49/50, major GNOME version jumps frequently **break existing extensions**. Always check compatibility in Extension Manager before updating or after a major distribution upgrade.

### Launching GNOME Tweaks Without a Menu Entry

On some distributions — particularly RHEL or minimal Fedora installs — GNOME Tweaks may not immediately appear in the application grid after installing it. Fix: press **Alt+F2**, type `gnome-tweaks`, press Enter.

**Example:** This same Alt+F2 run-dialog trick works for *any* newly installed application that hasn't shown up in your menu yet — a handy general troubleshooting habit, not just for Tweaks specifically.

---

## The Full Picture

The **Settings** app is your first stop for nearly everything — displays, network, date/time, users, and default apps — organized into a sidebar that's mostly intuitive, with the occasional setting tucked one level deeper than expected. When Settings comes up short — startup apps, advanced keyboard remapping, shell extensions — **GNOME Tweaks** and **GNOME Extensions** pick up the slack. Between the three, almost every configuration task on a modern Linux desktop is achievable without ever opening a terminal.

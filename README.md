
<p align="center">
  <img src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExdWszNGw0dDBrMGZnZjBpaGh5bDB4NHoyZmI0Yjl3bGM4dGMxeWU5diZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/8P4bnTyGQykuHxhWOm/giphy.gif" width="300" height="300" alt="REDIRMASK">
</p>

<h1 align="center">DEDSEC_REDIRMASK</h1>

<h4 align="center">Advanced link masking for ethical hackers, penetration testers and security-awareness teams</h4>

REDIRMASK is a link-masking tool for authorized phishing simulations, red-team engagements and security-awareness training. Pick a trusted-looking template (or a custom visible URL), enter the real destination, and REDIRMASK asks fourteen public shorteners in parallel for a short link. The final link shows the visible domain before `@`; the short link after it is what actually opens.

![Platform](https://img.shields.io/badge/platform-Linux%20x86--64-2ea44f)
![Version](https://img.shields.io/badge/version-4.1.0-blue)
![UI](https://img.shields.io/badge/UI-desktop%20GUI-8957e5)
![Runtime](https://img.shields.io/badge/runtime-self--contained-2ea44f)
![Root](https://img.shields.io/badge/root-not%20required-success)

> **Authorized use only.** Masked links are deceptive by design. Use REDIRMASK only with explicit written permission from the people and organizations you test. Never use it to collect credentials or personal data.

---

## Contents

- [What REDIRMASK does](#what-redirmask-does)
- [At a glance](#at-a-glance)
- [Requirements](#requirements)
- [Quick start](#quick-start)
- [Using the desktop UI](#using-the-desktop-ui)
- [Templates](#templates)
- [Tested on](#tested-on)
- [Legal disclaimer](#legal-disclaimer)

---

## What REDIRMASK does

- **Template masking** - choose from 64 presets modelled on Facebook, Instagram, Discord, YouTube, TikTok, GitHub, Steam, Spotify, Google Drive and more.
- **Custom masking** - supply the visible URL yourself when no preset fits.
- **Fourteen shorteners in one pass** - is.gd, v.gd, da.gd, clck.ru, spoo.me, zws.im, TinyURL, shrtr.top, r3rr.com, TheURLShortner, urlshort.at, URLVanish, asus.lol and Blinkhop (zou.sh) are contacted in parallel, and each answer appears as it arrives.
- **Copy-ready results** - copy the masked link or the underlying short link, or copy every working link at once.
- **Local history** - runs that produced at least one working link are stored under `~/.local/state/redirmask/history.json` and can be reopened in the builder.
- **Session log** - every selection, run, provider answer and history change is recorded in the UI.
- **Desktop only** - a pywebview window is the only interface; there is no command-line workflow.

### At a glance

| Feature | What it gives you |
| --- | --- |
| **Templates** | 64 presets grouped as Social, Chat, Media, Dev, Files, Shop, Gaming and Web3. |
| **Builder** | Visible mask URL, one target URL, one Generate button. |
| **Providers** | Fourteen shorteners contacted concurrently; no provider blocks another. |
| **Results** | Per-provider state, attempts, errors, masked link and real short link. |
| **History** | Up to 100 local runs, restorable into the builder, clearable from the UI. |
| **Log** | Timestamped session trail with severity colours. |

---

## Requirements

- Linux x86-64
- GTK 3
- WebKitGTK 4.1 with its GObject typelibs

Debian / Ubuntu / Kali:

```bash
sudo apt update
sudo apt install libgtk-3-0 libwebkit2gtk-4.1-0 \
                 gir1.2-gtk-3.0 gir1.2-webkit2-4.1
```

Package names differ slightly on other distributions. For example, Fedora uses `gtk3` and `webkit2gtk4.1`, and Arch uses `gtk3` and `webkit2gtk-4.1`.

---

## Quick start

Download the binary from this repository:

```bash
curl -LO https://github.com/0xbitx/DEDSEC_REDIRMASK/releases/latest/download/redirmask
chmod +x redirmask
./redirmask
```

If you downloaded the file through the GitHub web interface, it may already be named `redirmask`. Just make it executable and run it:

```bash
chmod +x dedsec_redirmask
./dedsec_redirmask
```
---

## Using the desktop UI

1. **Pick a template** from the library, or choose **Custom mask** and type the visible URL yourself. The filter accepts template names, hosts and groups; `/` focuses it.
2. **Enter the target URL** - the page the short link finally opens. A destination you control or are explicitly authorized to test is expected.
3. **Press Generate** (or `g`, or Enter inside a URL field). All fourteen shorteners are contacted in parallel and each result appears as it finishes. The run has a 22-second deadline.
4. **Open Results** and copy the masked link or the real short link. The app never opens a generated link.
5. **History** keeps every run with at least one working link. **Log** shows what happened in the current session.

The first window asks you to acknowledge the authorized-use terms. The acknowledgement is stored in the local browser profile and can be reviewed again from the About tab.

Other controls:

- **Zoom** - the `−` / `+` control in the top bar cycles 80–140%.
- **New mask** - clears the builder without touching history.
- **Shortcuts** - `g` generate, `/` filter, `?` guide, `Esc` close the open dialog or clear the filter.

### Run states

| State | Meaning |
| --- | --- |
| **READY** | The builder is idle and no generation is running. |
| **RUNNING** | At least one shortener thread is still working. |
| **DONE** | Every provider either answered or timed out. |
| **Provider OK** | A short link was returned and converted into a masked link. |
| **Provider FAILED** | The shortener answered without a usable link. |
| **Provider TIMEOUT** | No answer within the 22-second run deadline. |

History is saved only when at least one provider returns a usable link. A run where every provider fails leaves no history entry.

---

## Templates

The library ships **64 presets** across eight groups:

| Group | Presets | Examples |
| --- | ---: | --- |
| Social | 20 | Facebook, Instagram, TikTok, LinkedIn, Reddit, Twitter, Snapchat, Pinterest |
| Chat | 7 | Messenger, Discord invite/file, WhatsApp, Telegram |
| Media | 14 | YouTube live/video, Twitch, Netflix, Spotify, SoundCloud, Vimeo |

---

## Tested on

- Kali Linux
- Parrot OS
- Ubuntu

The binary targets Linux x86-64 with GTK 3 and WebKitGTK 4.1.

---

## Legal disclaimer

**WARNING** - REDIRMASK is intended for:

- Authorized penetration testing
- Security research and education
- Ethical hacking with explicit permission
- Red-team exercises with proper authorization
- Security-awareness training where the recipients have agreed to the exercise

Masked links are deceptive by design. Do not use them to collect passwords, payment details or other personal data. Do not target people who have not consented. Deceiving people or bypassing platform controls can be illegal in your jurisdiction.

**Unauthorized use of this tool is strictly prohibited and may violate local and international laws. Always ensure you have explicit permission before testing any system or individual. The developers are not responsible for misuse of this software.**


# MeetMeTV

Android for TV video calling app, built with Jetpack Compose and native WebRTC.

## 👋 What is this?

MeetMeTV is a video calling app made for the TV — a way to close the distance between the people
who matter, whether that's family who live far away, friends who don't get to visit often, or
anyone you'd rather see face-to-face than just hear on a phone call. Instead of huddling around a
small phone or laptop screen, everyone in the room can join a 1:1 or group video call together, on
the biggest screen in the house.

## ✨ Features

- 📹 **1:1 video/voice calling** — outgoing and incoming, adaptive bitrate/resolution based on
  live network conditions, hardware H.264 encoding confirmed working on real devices.
- 👥 **Group video calling** (3-4 participants, mesh topology) — collapses to a 1:1-style layout
  as participants leave, supports rejoining an in-progress call at any time.
- 📇 **Contacts & Call History** — stored locally on-device.
- 🗂️ **Groups** — saved rosters for group calling, local-only.
- 👤 **Profile** — identity/handle, avatar, a device PIN lock, and encrypted backup export/import
  (byte-for-byte compatible with the original WebView app's own backup format).
- ⚙️ **Configurable TURN** — ExpressTURN, Metered.ca, Turnix.io, or a custom server, plus a
  built-in webcam/mic preview and diagnostics screen.
- ⭐ **A "MeetMeTV Favorites" launcher channel** — call a favorited contact directly from the
  Android TV/Google TV home screen without opening the app first.
- 🔔 **On-screen incoming-call notification** — a small banner in the top-right corner alerts you
  to an incoming call even while you're watching or browsing something else, so you never miss
  one. Can be turned off in Settings if you'd rather not use it.
- 🟢 **At-a-glance contact status** — a small dot on each contact's avatar shows whether they're
  reachable right now: 🟢 green means online, 🟡 yellow means away, 🔴 red means they're already
  on a call, and a gray power-off icon means they're currently offline/unreachable.

## 🛠️ How it works (technical summary)

- **Native, not browser-based** — calls run through a native video engine built directly for
  Android TV hardware, reaching the device's own hardware video encoder/decoder directly instead
  of going through a browser-based video stack.
- **Adaptive bandwidth** — captures video at the camera's real maximum resolution and steps
  through a resolution ladder based on live network conditions, so quality adapts smoothly instead
  of freezing or dropping the call.
- **Relay-assisted connectivity** — a configurable relay handles connectivity for calls across
  different networks (e.g. one side on mobile data, the other on home broadband).
- **Local-only data** — Contacts, Call History, and Groups live entirely on-device, not on a
  shared server.
- **TV home screen integration** — a real home-screen launcher row for favorite contacts, and
  picture-in-picture support during an active call.

## 💬 Support & feedback

Found a bug or have a feature request? Open an issue on this repository.

## 📄 License

Proprietary. Unauthorized copying, modification, reverse engineering, or redistribution is
prohibited.

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
- 👥 **Group video calling** (up to 5 participants, mesh topology) — collapses to a 1:1-style layout
  as participants leave, supports rejoining an in-progress call at any time.
- 📇 **Contacts & Call History** — stored locally on-device.
- 🗂️ **Groups** — saved rosters for group calling, local-only.
- 👤 **Profile** — handle, avatar, a device PIN lock, and encrypted backup export/import.
- ⚙️ **Configurable TURN** — ExpressTURN, Metered.ca, Turnix.io, or a custom server, plus a
  built-in webcam/mic preview and diagnostics screen.
- ⭐ **A "MeetMeTV Favorites" launcher channel** — call a favorited contact directly from the
  Android TV/Google TV home screen without opening the app first.
- 🔔 **On-screen incoming-call notification** — a small banner in the top-right corner alerts you
  to an incoming call even while you're watching or browsing something else, so you never miss
  one. Can be turned off in Settings if you'd rather not use it.
- 👁️ **At-a-glance contact status** — a small dot on each contact's avatar shows whether they're
  reachable right now: 🟢 green means online, 🟡 yellow means away, 🔴 red means they're already
  on a call, and a 🔌 gray power-off icon means they're currently offline/unreachable.
- 🖼️ **Picture-in-Picture** — shrink an active call down and keep it running while you go back to
  the TV's own home screen. There's also an in-app floating call window that works on every device
  regardless of that support, letting you shrink the call into a small corner and keep browsing the
  rest of MeetMeTV without leaving it at all.
- 🤓 **"Stats for Nerds"** — an optional overlay during a call showing the real technical numbers
  behind it: video resolution, bitrate, and packet loss in each direction, network latency, and
  how the call is actually connected (direct, or relayed through a server). Useful for checking
  call quality or troubleshooting a shaky connection - completely optional to look at.
- 🔒 **Hardware-backed account security** — each device generates its own cryptographic identity
  key inside its own secure hardware chip. The private key itself never leaves that chip — not
  even when exporting/importing a profile backup, which carries a signed permission slip instead
  of the key. The server verifies that signature before ever letting a device join your account,
  so nobody can hijack your handle or impersonate your device — not even with a modified copy of
  the app.

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

## ⚠️ Technical Limitations

These technical limitations are tied more to the hardware itself than to the app in general:

- Not every device has hardware encoding support - when that's the case, the supported resolution
  will be limited to something lower than what the camera itself supports, and on top of that, the
  device will run hotter and may reboot if it gets hotter than it can handle. You can check if your device has hardware encoding support by going to settings -> Webcam Settings where you will see the confirmation at the top of the card. If you want hardware
  encoding on your device, please reach out to the manufacturer.
- The Google TV Streamer has hardware encoding issues where the resolution isn't stable; on top of
  that, the camera can freeze at any moment, requiring a device reboot to fix it. This was reported
  at Google's own Issue Tracker: https://issuetracker.google.com/issues/546793415 - feel free to
  leave a comment there asking for a prompt fix.
- The Google TV Streamer is unable to detect the microphone of some webcams, specially from generic ones.
- Picture-in-Picture isn't universally supported - several devices likely don't support it, or
  used to but no longer do, so the video call will simply end when pressing Home on a device
  without support. The only tested device confirmed to support it so far is the Google TV
  Streamer - you can check this yourself in the "Other Settings" tab.

## 💬 Support & feedback

Found a bug or have a feature request? Open an issue on this repository.

## 📄 License

Proprietary. Unauthorized copying, modification, reverse engineering, or redistribution is
prohibited.

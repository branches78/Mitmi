# Mitmi

Private video calls on your TV for free, baked with WebRTC, with no ads and no tracking.

## 👋 What is it?

Mitmi is a video calling app made for the TV — a way to close the distance between the people
who matter, whether that's family who live far away, friends who don't get to visit often, or
anyone you'd rather see face-to-face than just hear on a phone call. Instead of huddling around a
small phone or laptop screen, everyone in the room can join a 1:1 or group video call together, on
the biggest screen in the house.

## ✨ Features

- 📹 **1:1 video/voice calling** — outgoing and incoming, adaptive bitrate/resolution based on
  live network conditions, hardware H.264 and H.265 encoding confirmed working on real devices.
- 👥 **Group video calling** (up to 5 participants, mesh topology) — collapses to a 1:1-style layout
  as participants leave, supports rejoining an in-progress call at any time.
- 📇 **Contacts & Call History** — stored locally on-device.
- 🗂️ **Groups** — saved rosters for group calling, local-only.
- 👤 **Profile Settings** — You can customize your avatar and to setup a 4 digit PIN lock
  to protect your profile from unwanted users as well as other sensitive parts of the interface.
- 📹 **Camera Preview** — It allows you check if the camera and microphone are detected correctly,
  as well as the type of encoding supported by the device (hardware or software).
- ⚙️ **Configurable TURN Server (optional)** — ExpressTURN, Metered.ca, Turnix.io, or a custom server
  and it's needed only in case that some calls don't go through with Point to Point or with a STUN Server.
- ⭐ **A "Mitmi Favorites" launcher channel** — call a favorited contact directly from the
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
  rest of Mitmi without leaving it at all.
- 🤓 **Stats for Nerds** — an optional overlay during a call showing the real technical numbers
  behind it: video resolution, bitrate, and packet loss in each direction, network latency, and
  how the call is actually connected (direct, or relayed through a server). Useful for checking
  call quality or troubleshooting a shaky connection - completely optional to look at.
- 🔗 **Add a second device** — You can add up to 2 devices with a short code, valid for one minute.
  Enter it on the new device (both online) and your profile, contacts and groups carry over.
- 💾 **Export/Import a profile backup** — You can import your profile on up to 2 devices, as well as
  to save the export for one-time future use, such as when you need to replace your current device
  with a new one because it got damaged or broken or it's just old.

## 🛠️ How it Works

- **Native, not browser-based** — built with Jetpack Compose and native WebRTC, calls run through
  a native video engine built directly for Android TV hardware, reaching the device's own hardware
  video encoder/decoder directly instead of going through a browser-based video stack.
- **Peer-to-Peer Encryption** — Video and audio streams are transmitted directly between devices using
  WebRTC with SRTP/DTLS encryption, keeping third parties out.
- **Zero Server Stream Storage** — No audio or video recordings are ever stored on servers. Your live
  call media exists strictly in real time.
- **Hardware Encoding Support** — AV1, H264 and H265 Hardware Encoding is supported as long as
  the device supports it, you can check the codec and the type of encoding used (hardware or software)
  in the "Webcam Settings" tab and at the "Stats for Nerds".
- **Adaptive bandwidth** — captures video at the camera's real maximum resolution and steps
  through a resolution ladder based on live network conditions, so quality adapts smoothly instead
  of freezing or dropping the call.
- **Local-only data** — Contacts, Call History, and Groups live entirely on-device, not on a
  shared server.
- **Hardware-backed account security** — each device generates its own cryptographic identity
  key inside its own secure hardware chip. The private key itself never leaves that chip — not
  even when exporting/importing a profile backup, which carries a signed permission slip instead
  of the key. The server verifies that signature before ever letting a device join your account,
  so nobody can hijack your handle or impersonate your device — not even with a modified copy of
  the app.
  
## 📒 How to Obtain & Add Contacts
  
- Every user on Mitmi has a unique username handle (for example: @sarah_chen or @living_room).
- Ask for Their Username Handle — Request your friend or family member's @username to connect directly.
- Save in Address Book — Use the Contacts tab to add them to your directory or type their handle
  into search to dial immediately without saving.

## ⚠️ Technical Limitations

- Not every device has hardware encoding support, when that's the case, the supported resolution
  will be limited to something lower than what the camera supports compared to hardware encoding
  and on top of that, the device will run hotter and may reboot if it gets hotter than it can handle.
  You can check if your device has hardware encoding support by going to "Settings" → "Webcam Settings"
  where you will see the confirmation at the top of the card. If you want hardware encoding on your
  device, please reach out to the manufacturer.
- Picture-in-Picture isn't universally supported, several devices likely don't support it, or
  used to but no longer do, so the video call will simply end when pressing the Home button on
  the remote control. The only tested device confirmed to support it so far is the Google TV
  Streamer. You can get a confirmation about this in "Settings" → "Other Settings" tab.
- For some reason, the microphone on some webcams is not detected by one particular device
  but the same microphone is detected by a different device. This limitation has nothing
  to do with the application but with the device's firmware.

## 🚨 Current Hardware Issues

The Google TV Streamer has hardware encoding issues with the H.264 and H.265 codecs, which were reported
at Google's Issue Tracker website [here](https://issuetracker.google.com/issues/546793415) and [here](https://issuetracker.google.com/issues/564530609) - feel free to leave a comment there asking for a prompt fix.

## 💬 Support & Feedback

Found a bug or have a feature request? Open an issue on this repository.

## 📄 License

Proprietary. Unauthorized copying, modification, reverse engineering, or redistribution is
prohibited. Please check the Terms & Conditions and Privacy Policy before creating a handle,
at the Mitmi [website](http://mitmi-web.onrender.com) and at the bottom of the "About" tab.

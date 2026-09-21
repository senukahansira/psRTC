# Random Video Chat

<p align="center">
  <img src="https://img.shields.io/badge/Go-1.26-00ADD8?style=for-the-badge&logo=go" alt="Go" />
  <img src="https://img.shields.io/badge/JavaScript-ES6-F7DF1E?style=for-the-badge&logo=javascript" alt="JavaScript" />
  <img src="https://img.shields.io/badge/WebRTC-Real%20Time-333333?style=for-the-badge" alt="WebRTC" />
  <img src="https://img.shields.io/badge/Mode-Video%20%2B%20Chat-4A90E2?style=for-the-badge" alt="Modes" />
</p>

A lightweight real-time random chat app that matches strangers instantly and lets them connect in either text chat or live video chat.

## ✨ What's it does.

- Randomly pairs users in real time
- Supports both video and chat-only modes
- Uses WebRTC for peer-to-peer video communication
- Uses WebSockets for signaling and matchmaking
- Lets users switch to a new stranger with the Next button

## 🧩 Tech stack

### Frontend
- HTML5
- CSS3
- Vanilla JavaScript
- WebRTC APIs (`RTCPeerConnection`, `RTCIceCandidate`)
- Media capture via `getUserMedia()`

### Backend
- Go
- Gorilla WebSocket
- Standard Go HTTP server

### Real-time networking
- WebSocket signaling for offers, answers, ICE candidates, and chat messages
- STUN server for NAT traversal
- Peer-to-peer media negotiation

## 🏗️ How it works

1. A user opens the app in the browser.
2. They choose either Video Only or Chat Only.
3. The Go server places them into the correct waiting queue.
4. When a match is found, the server assigns a session and role.
5. The browser and server exchange WebRTC signaling data.
6. A peer connection is created and the media or chat channel is established.

## 📁 Project structure

```text
.
├── app.js          # Frontend logic, WebRTC negotiation, UI state
├── index.html      # App layout and interface
├── main.go         # Go signaling server and matchmaking logic
├── go.mod          # Go module configuration
├── go.sum          # Dependency lockfile
└── README.md       # Project documentation
```

## 🛠️ Key implementation ideas

- Matchmaking is handled in Go with separate waiting queues for chat and video sessions.
- The browser manages signaling, session state, and media streams in JavaScript.
- ICE candidates are queued until remote SDP has been set, ensuring stable negotiation.
- The app supports graceful session reset, reconnection, and partner disconnect handling.

<img width="1366" height="619" alt="WhatsApp Image 2026-09-19 at 12 29 34 AM(1)" src="https://github.com/user-attachments/assets/7b5be60e-a953-425a-8033-7661298d3798" />
<img width="1366" height="619" alt="WhatsApp Image 2026-09-19 at 12 29 34 AM" src="https://github.com/user-attachments/assets/d28f5d60-ee4e-484d-8a53-e28a97ff7d37" />
<img width="1366" height="619" alt="WhatsApp Image 2026-09-19 at 12 29 33 AM" src="https://github.com/user-attachments/assets/a546c13e-47f6-4a0d-acac-f50cb3daa953" />

## Author

Built by [senuka hansira](https://github.com/senukahansira) , [paboda dasanayaka](https://github.com/Paboda113)

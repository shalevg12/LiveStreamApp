# LiveStreamApp

**LiveStreamApp** is an iOS project written in Swift, consisting of two applications – **ClientApp** and **DirectorApp** – enabling real-time video streaming over a local Wi-Fi network between iPhones and iPads. The system uses peer-to-peer connectivity to broadcast live video streams from multiple clients to a central director device, with remote control capabilities and media saving.

---

## 🔍 Overview

This project was created to support live, multi-camera workflows for events, video productions, or documentation scenarios.  
**As a freelance videographer and editor myself**, I use this app regularly to monitor and record multiple iPhones on set from a central iPad.

---

## 🎯 Features

- 📷 **Live video stream** from multiple iPhones to a central iPad.
- 🖼️ **Grid view display** for real-time monitoring of multiple camera feeds.
- 🎛️ **Remote control** for taking photos and starting/stopping video recording.
- 💾 **Automatic video saving** to the device gallery.
- 📡 **P2P connection** via MultipeerConnectivity.

---

## 🧰 Technologies

| Domain | Stack |
|--------|-------|
| Language | Swift 5 |
| Frameworks | SwiftUI, AVFoundation, Combine |
| Networking | MultipeerConnectivity (P2P over Wi-Fi) |
| Design Patterns | MVVM, Component-Based UI |
| Platforms | iOS 16+ |
| Tools | Xcode, Instruments, XCTest (optional) |

---

## 📁 Project Structure

LiveStreamApp  
├── ClientApp              # iPhone app – sends video stream  
│   ├── Models             # Camera configuration and data models  
│   ├── Services           # CameraService, MPCManager for streaming & commands  
│   ├── Views              # Live preview UI  
│   └── ClientApp.swift    # App entry point  
│  
├── DirectorApp           # iPad app – receives and displays streams  
│   ├── Models             # CameraStream model  
│   ├── Services           # MPCReceiverService for receiving media & commands  
│   ├── Views              # VideoGridView, MainView  
│   └── DirectorApp.swift  # App entry point  
│  
└── README.md              # Project documentation  

---


## 🚀 Getting Started

Follow these instructions to set up and run both parts of the project locally on real iOS devices.

### Prerequisites

- Xcode 15+
- Swift 5.9+
- Two or more physical iOS devices (e.g., iPhone and iPad) connected to the same Wi-Fi network
- An Apple Developer account for signing and provisioning

---

### 🔧 Setup Instructions

1. **Clone the repository**

   ```bash
   git clone https://github.com/shalevg12/LiveStreamApp.git
   cd LiveStreamApp
   ```

2. **Open the apps in Xcode**

   - Open `ClientApp` in Xcode to run on an iPhone.
   - Open `DirectorApp` in Xcode to run on an iPad.

3. **Configure signing**

   - Go to the **Signing & Capabilities** section in each target.
   - Select your Apple developer team.
   - Make sure each app has a unique bundle identifier, for example:
     - `com.yourname.ClientApp`
     - `com.yourname.DirectorApp`

4. **Run the apps**

   - Connect each device to your Mac (USB or wireless).
   - Select the correct device in the Xcode toolbar.
   - Press **Run** for both apps.

   > ⚠️ Ensure both devices are connected to the same local Wi-Fi network.

---

## 🧪 Features

### ClientApp (iPhone)
- Live camera preview using `AVCaptureSession`
- Real-time video frame streaming via `MultipeerConnectivity`
- Receives remote commands from DirectorApp:
  - 📸 Capture Photo
  - 🔴 Start Video Recording
  - ⏹️ Stop Video Recording
- Saves captured media locally to the photo library

### DirectorApp (iPad)
- Connects to multiple Client devices over LAN
- Displays all video streams in a responsive grid layout
- Tap to enlarge a specific stream
- Sends remote control commands to each peer
- Saves received videos directly to the device photo library

---

## 🧰 Technologies Used

- **SwiftUI** – Declarative UI framework for iOS apps
- **MultipeerConnectivity** – Peer-to-peer local networking
- **AVFoundation** – Camera control and media recording
- **Photos Framework** – Access and save media to the device
- **Combine** – Reactive programming for state updates
- **UIKit** – Integrated for advanced functionality where required

---

## 📁 Project Structure

LiveStreamApp  
├── ClientApp – iPhone app that streams video  
│   ├── Models – Camera settings and configuration  
│   ├── Services – `CameraService`, `MPCManager` for stream/command handling  
│   ├── Views – Camera preview interface  
│   └── ClientApp.swift – Main app entry point  
│  
├── DirectorApp – iPad app that receives and displays streams  
│   ├── Models – Stream data models  
│   ├── Services – `MPCReceiverService` for communication  
│   ├── Views – Grid and full-screen viewer  
│   └── DirectorApp.swift – Main app entry point  
│  
└── README.md – Project documentation  

---

## 👤 About the Developer

I am a Software Engineer and iOS developer and UI designer with a strong background in video production.  
This app was fully designed and developed by me, from architecture and UI to testing and deployment.

As a freelance videographer and video editor myself, I actively use this app on real productions to monitor and control multiple camera angles in real-time, directly from an iPad.

---

## 📸 Example Use Case

A director on a live production set uses an iPad (running DirectorApp) to monitor several iPhones (each running ClientApp) placed around the set.  
From a single interface, the director can preview all streams, record remotely, capture stills, and receive the footage in seconds – without touching the client devices.

---

## 🧭 Future Improvements

- Live audio streaming integration
- Cloud-based syncing and media storage
- Visual overlays (recording status, battery, connectivity)
- External screen support for director interface
- Cross-platform support (e.g., Android/Web via WebRTC)

---

## 📄 License

This project is open source and licensed under the [MIT License](LICENSE).  
Feel free to use, modify, and contribute to the project.

# 🚀 Web2APK Pro

<p align="center">
  <img src="https://img.shields.io/badge/Version-1.0.0-blue?style=for-the-badge&logo=github" alt="Version">
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge&logo=opensourceinitiative" alt="License">
  <img src="https://img.shields.io/badge/Runtime-Node.js-green?style=for-the-badge&logo=node.js" alt="Runtime">
  <img src="https://img.shields.io/badge/Platform-Android%20%7C%20Web-purple?style=for-the-badge&logo=android" alt="Platform">
  <img src="https://img.shields.io/badge/Status-Production%20Ready-success?style=for-the-badge" alt="Status">
</p>

<p align="center">
  <h3 align="center"> The Ultimate Web-to-Native Android APK Builder & Management Toolkit</h3>
  <p align="center">
    Seamlessly convert web applications into fully functional, permission-aware Android APKs with background execution, real-time diagnostics, and a premium mobile-first UI.
  </p>
</p>

<p align="center">
  <a href="#-overview">Overview</a> •
  <a href="#-visual-showcase">Showcase</a> •
  <a href="#-core-features">Features</a> •
  <a href="#-architecture">Architecture</a> •
  <a href="#-usage-guide">Usage</a> •
  <a href="#-author">Author</a>
</p>

---

##  Overview

**Web2APK Pro** is a professional-grade development and security research tool designed to rapidly package web applications into native Android APKs. Built on a robust **Node.js** backend, it features a clean, intuitive web interface that generates signed, permission-configured APKs in seconds.

Unlike basic web-to-app wrappers, Web2APK Pro includes a comprehensive **Permission Management System**, **Background Execution Services**, and built-in **Utility Modules** (Internet Check, Web Search, File Uploads). 

> 💡 **Note:** This repository serves as the official **Proof of Concept (POC)** and documentation hub, showcasing the tool's capabilities, UI/UX design, and architectural flow.

---

##  Visual Showcase (POC)

### ️ Phase 1: Web Builder Interface (Node.js Backend)

| Server Initialization | Configuration UI |
| :---: | :---: |
| ![Server Startup](screenshots/01_nodejs_server_startup.png) | ![Web UI Builder](screenshots/02_web_ui_builder_interface.png) |
| *Terminal launching `node server.js` on `localhost:3000`* | *Full configuration: Paths, Metadata, and Permissions* |

| Asset Management | Build & Download |
| :---: | :---: |
| ![Icon Upload](screenshots/03_icon_upload_file_picker.png) | ![APK Download](screenshots/04_apk_build_and_download.png) |
| *Custom PNG/JPG icon selection via native file picker* | *Successful build: "APK Download Started!" (37.3 KB)* |

---

### 📱 Phase 2: Android Installation & Execution

| Installation | File System |
| :---: | :---: |
| ![App Installed](screenshots/06_apk_installation_notification.png) | ![APK in Downloads](screenshots/07_downloads_folder_apk.png) |
| *Native Android "App installed" notification* | *Generated `webapk.apk` in device storage* |

| Launcher Integration |
| :---: |
| ![Home Screen](screenshots/05_android_home_screen_icon.png) |
| *Custom app icon successfully installed on Android launcher* |

---

### 🔐 Phase 3: Granular Permission System (Runtime)

| Camera Request | Camera Verified | Audio Request |
| :---: | :---: | :---: |
| ![Camera Permission](screenshots/09_camera_permission_dialog.png) | ![Camera Working](screenshots/10_camera_access_working.png) | ![Audio Permission](screenshots/11_audio_permission_dialog.png) |
| *Native Camera/Video prompt* | *Viewfinder active & granted* | *Microphone access prompt* |

| Location (Granular) | Storage (Elevated) |
| :---: | :---: |
| ![Location Permission](screenshots/12_location_permission_dialog.png) | ![Storage Permission](screenshots/13_all_files_access_permission.png) |
| *Precise vs. Approximate selection* | *MANAGE_EXTERNAL_STORAGE for v1.0* |

---

### ️ Phase 4: Background Execution & Utilities

| Background Service | Network Diagnostics |
| :---: | :---: |
| ![Background Running](screenshots/08_active_apps_background.png) | ![Internet Check](screenshots/14_internet_check_module.png) |
| *System-level "Active apps" management* | *Real-time speed (45 Mbps) & latency (28ms)* |

| Web Search Engine | Search Results |
| :---: | :---: |
| ![Web Search](screenshots/15_web_search_module.png) | ![Search Results](screenshots/16_web_search_results.png) |
| *Integrated in-app search bar* | *Google results rendered in WebView* |

| File Uploads | Master Dashboard |
| :---: | :---: |
| ![File Uploads](screenshots/17_file_uploads_module.png) | ![Dashboard](screenshots/18_features_dashboard.png) |
| *Drag & drop document/media support* | *Complete utility module overview* |

---

## 🟣 Core Features

| 🟢 Feature | 🔵 Description |
| :--- | :--- |
| ** Node.js Backend** | Lightweight, fast server running on `localhost:3000` via `node server.js`. |
| **🎨 Custom Branding** | Fully customizable App Name, Package Name (`com.example.app`), and PNG/JPG Icons. |
| **🛡️ Granular Permissions** | Toggle Camera, Audio, Location, Storage, Background, Internet, Admin Controls, and Screen Capture. |
| **🔄 Background Execution** | Native Android foreground services for persistent background running with UI controls. |
| **📶 Network Diagnostics** | Built-in "Internet Check" utility providing real-time Speed (Mbps) and Latency (ms) metrics. |
| **🔍 Web Search** | Integrated, customizable search engine rendered seamlessly inside the app. |
| **📂 File Uploads** | Native drag-and-drop support for documents, images, and videos. |
| ** Real-Time Build** | Instant APK generation (~37 KB) with immediate browser download notifications. |
| **💎 Premium UI/UX** | Dark-themed, mobile-first design with soft gradient accents and rounded cards. |

---

## 🏗️ Architecture

```text
┌─────────────────────────────────────────────────────────────────────┐
│  🖥️ CONTROL PLANE: Web Builder Interface (Node.js - Port 3000)      │
│  ┌───────────────────────────────────────────────────────────────┐  │
│  │  [Folder Path]  [App Name]  [Package Name]  [Icon Upload]     │  │
│  │  [Permissions Matrix: Camera, Audio, Location, Storage...]    │  │
│  └───────────────────────────────────────────────────────────────┘  │
│                              │                                      │
│                              ▼                                      │
│  ┌───────────────────────────────────────────────────────────────┐  │
│  │  ⚙️ BUILD ENGINE: Manifest Generator + Asset Packager + Signer│  │
│  └───────────────────────────────────────────────────────────────┘  │
│                              │                                      │
│                              ▼                                      │
│  ┌───────────────────────────────────────────────────────────────┐  │
│  │  📦 OUTPUT: Signed webapk.apk (~37 KB) → HTTP Download Stream │  │
│  └───────────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────────┐
│  📱 EXECUTION PLANE: Android Device                                  │
│  ┌───────────────────────────────────────────────────────────────┐  │
│  │   Installation → 🔐 Runtime Permission Bridge               │  │
│  │   WebView Controller + 📷 Native Modules (Cam, Audio, Loc)  │  │
│  │  🔄 Background Service + 📊 Utility Dashboard (Speed/Search)  │  │
│  └───────────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────────┘

<div align="center">
  <br />
  <img src="pages/image/logo.png" alt="CodeGap Logo" width="120" />
  <br />
  <h1 align="center">CodeGap</h1>
  <p align="center">
    <strong>Next-Gen Cloud IDE & Prototyping Engine</strong>
  </p>
  <p align="center">
    Build, Edit, and Run HTML/CSS/JS projects directly in the browser with real-time cloud synchronization.
  </p>

  <p align="center">
    <a href="https://computerboy-dev.github.io/codeGap/">
      <img src="https://img.shields.io/github/deployments/yourusername/codegap/github-pages?style=for-the-badge&logo=github&label=Deployed%20on%20GitHub%20Pages" alt="Deployment Status" />
    </a>
  </p>
  
  <p align="center">
    <img src="https://img.shields.io/badge/Architecture-Serverless-blueviolet?style=for-the-badge" />
    <img src="https://img.shields.io/badge/Editor-Monaco_Engine-1e1e1e?style=for-the-badge&logo=visualstudiocode" />
    <img src="https://img.shields.io/badge/Database-Firestore-orange?style=for-the-badge&logo=firebase" />
    <img src="https://img.shields.io/badge/Styling-Tailwind_CSS-38bdf8?style=for-the-badge&logo=tailwindcss" />
  </p>

  <br />
</div>

---

## 📖 Table of Contents
- [🚀 Overview](#-overview)
- [✨ Key Features](#-key-features)
- [🏗️ System Architecture](#-system-architecture)
- [🛠️ Tech Stack](#-tech-stack)
- [💻 Usage Guide](#-usage-guide)
  - [Terminal Commands](#terminal-commands)
  - [Keyboard Shortcuts](#keyboard-shortcuts)
- [🔧 Installation & Setup](#-installation--setup)
- [🛡️ Security & Performance](#-security--performance)
- [🤝 Contributing](#-contributing)

---

## 🚀 Overview

**CodeGap** is a sophisticated **Browser-Based Integrated Development Environment (IDE)** inspired by tools like CodePen and Replit. It solves the problem of local environment setup by providing a zero-config, instant-start coding platform accessible from any desktop browser.

Unlike traditional text editors, CodeGap features a **Virtual File System (VFS)** that runs entirely in the client's memory, allowing users to create complex folder structures, manage files, and execute terminal commands without needing a backend server for file management. All progress is seamlessly synced to **Firebase Firestore**, ensuring continuity across sessions.

---

## ✨ Key Features

### 👨‍💻 Professional Coding Interface
* **Monaco Editor Integration:** Powered by the same engine as VS Code, featuring syntax highlighting, IntelliSense, code folding, and minimaps.
* **Desktop-First UX:** Optimized for large screens with draggable panels, resizable terminal, and split-screen layouts.

### 📂 Virtual File System (VFS)
* **In-Memory Management:** A custom JavaScript-based file system that supports `CRUD` operations (Create, Read, Update, Delete) instantly.
* **Terminal Simulation:** A built-in CLI that interacts with the VFS using Unix-like commands (`ls`, `mkdir`, `touch`, `rm`).

### ☁️ Cloud & Synchronization
* **Real-Time Sync:** Leveraging Firestore's `onSnapshot` listeners to sync project state across devices.
* **Debounced Saving:** Implements a smart save strategy (800ms debounce) to minimize database write costs while ensuring data integrity.
* **Auto-Recovery:** Projects are automatically loaded from the cloud upon login.

### ⚡ Instant Compilation Engine
* **Client-Side Rendering:** Uses a custom `Blob URL` injection technique to compile HTML, CSS, and JS into a previewable iframe without server-side processing.
* **Smart Resolution:** Automatically detects relative paths in `<link>` and `<script>` tags and injects the corresponding content from the VFS.

<div align="center"> <h3>Designed & Developed by <a href="https://github.com/computerBoy-dev">Aaryan</a></h3> <p> Built with ❤️ and ☕ for developers. </p> </div>

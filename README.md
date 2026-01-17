<div align="center">
  <img src="pages/image/logo.png" alt="CodeGap Logo" width="100" />
  <br />
  <h1>CodeGap</h1>
  <p>
    <strong>A Cloud-Native, Browser-Based IDE for Modern Web Development</strong>
  </p>
  
  <p>
    <a href="https://firebase.google.com/"><img src="https://img.shields.io/badge/Backend-Firebase-orange?style=for-the-badge&logo=firebase" alt="Firebase" /></a>
    <a href="https://tailwindcss.com/"><img src="https://img.shields.io/badge/Styling-Tailwind_CSS-38bdf8?style=for-the-badge&logo=tailwindcss" alt="Tailwind" /></a>
    <a href="https://microsoft.github.io/monaco-editor/"><img src="https://img.shields.io/badge/Editor_Engine-Monaco-blue?style=for-the-badge&logo=visualstudiocode" alt="Monaco" /></a>
    <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript"><img src="https://img.shields.io/badge/Language-Vanilla_JS-yellow?style=for-the-badge&logo=javascript" alt="JavaScript" /></a>
  </p>

  <p>
    <a href="#features">Features</a> •
    <a href="#architecture">Architecture</a> •
    <a href="#getting-started">Getting Started</a> •
    <a href="#demo">Live Demo</a>
  </p>
</div>

---

## 🚀 Overview

**CodeGap** is a sophisticated, browser-based Integrated Development Environment (IDE) designed to replicate the desktop coding experience in the cloud. Built with a focus on **performance** and **real-time synchronization**, it allows developers to write, edit, and preview HTML/CSS/JS projects instantly without any local setup.

Unlike simple text areas, CodeGap integrates the **Monaco Editor** (the core of VS Code) to provide Intellisense, syntax highlighting, and code formatting. It features a custom **Virtual File System (VFS)** and a simulated **Terminal**, making it a robust tool for rapid prototyping.

## ✨ Key Features

### 🛠️ Core Engineering
* **Monaco Editor Integration:** Full-featured code editing experience with syntax highlighting, auto-completion, and minimap support.
* **Virtual File System (VFS):** A custom-engineered in-memory file system supporting file/folder creation, deletion, and renaming (`CRUD` operations) purely on the client side.
* **Real-Time Cloud Sync:** Leveraging **Firebase Firestore**, every keystroke and file change is debounced and synchronized to the cloud, ensuring work is never lost.
* **Instant Live Preview:** Implements a unique **Blob URL injection engine** that compiles HTML, CSS, and JS in real-time within a sandboxed `iframe`, eliminating the need for server-side rendering.

### 🖥️ User Experience (UX)
* **Integrated Terminal:** A simulated command-line interface (CLI) supporting Unix-like commands (`ls`, `mkdir`, `touch`, `rm`, `cat`) to interact with the project structure.
* **Authentication System:** Secure login via **Google OAuth** and **Passwordless Email Links** using Firebase Auth.
* **Project Management:** Dashboard to view project history, track "Last Updated" timestamps, and manage multiple projects.
* **Export Capability:** One-click project export functionality that bundles the virtual file structure into a downloadable **ZIP archive** using `JSZip`.

---

## 🏗️ Technical Architecture

CodeGap operates on a **Serverless Architecture**, relying heavily on client-side logic for performance.

### 1. The Compilation Engine
Instead of sending code to a server to be rendered, CodeGap handles compilation locally:
> The engine parses the `index.html`, identifies linked CSS/JS files within the Virtual File System, and injects their content dynamically into the DOM. This bundle is converted into a `Blob` object and served to the preview iframe.

### 2. The Virtual Terminal
The terminal is not a connection to a backend shell but a JavaScript emulation that interacts with the `files` object graph:
```javascript
// Example Logic
function runCommand(cmd) {
  if (cmd === "ls") return Object.keys(files);
  if (cmd.startsWith("mkdir")) createVirtualFolder(args);
  // ...
}

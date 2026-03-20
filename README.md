# ⬜ Light Code Editor (LCE)

<div align="center">

██╗      ██████╗███████╗
██║     ██╔════╝██╔════╝
██║     ██║     █████╗

██║     ██║     ██╔══╝

███████╗╚██████╗███████╗
╚══════╝ ╚═════╝╚══════╝

**Ultra-lightweight. Monochrome. Productive.**

[![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)](https://www.rust-lang.org/)
[![Tauri](https://img.shields.io/badge/Tauri-000000?style=for-the-badge&logo=tauri&logoColor=white)](https://tauri.app/)
[![React](https://img.shields.io/badge/React-000000?style=for-the-badge&logo=react&logoColor=white)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-000000?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)

</div>

---

## Philosophy: Lightweight & Modern

Light Code Editor was born from a simple conviction: **a code editor should consume
fewer resources than the code it edits.**

In a world where text editors consume 500MB+ of RAM just to display "Hello World,"
LCE takes the opposite approach:

- **< 80MB RAM** at runtime — lighter than a browser tab
- **< 15MB** distributable binary — smaller than most images
- **< 1 second** cold start — faster than your terminal
- **Zero telemetry** — your code stays yours

### Design Principles

1. **Monochrome Focus**: Pure black & white interface eliminates visual noise.
   Your code is the only color on screen.
2. **Command-First**: No toolbar hunting. Every action through `Ctrl+Shift+P`.
3. **Native Performance**: Rust backend with Rope data structures handles
   files that would crash other editors.
4. **Bidirectional Editing**: Edit code → see preview. Click preview → jump to code.

---

## Features

| Feature | Description |
|---------|-------------|
| 🔤 **Rope Engine** | Edit 100MB+ files without lag using `ropey` |
| 🌳 **Tree-sitter** | Syntax highlighting that understands your code |
| 🔄 **Live Preview** | Bidirectional sync between code and rendered output |
| 🧠 **LSP Integration** | Native Language Server Protocol for intelligence |
| 📦 **Git Desktop** | Stage, commit, push, pull, and visual diffs |
| 🔍 **Layout Inspector** | Built-in DevTools for CSS box model inspection |
| 🖼️ **Stock Images** | Search Unsplash/Pexels and drag into your project |
| ⌨️ **Command Palette** | Every action, zero mouse required |

---

## Quick Start

### Prerequisites

```bash```bash
# Install Rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Install Node.js 18+
# https://nodejs.org/

# Install Tauri CLI
cargo install tauri-cli

# Development
# Clone the repository
git clone https://github.com/your-org/light-code-editor.git
cd light-code-editor

# Install frontend dependencies
cd src-ui
npm install
cd ..

# Run in development mode
cargo tauri dev

# Build for Production
# Build optimized release
cargo tauri build



| Platform | Format | Path |
| :--- | :--- | :--- |
| 🪟 **Windows** | `.exe`, `.msi` | `src-tauri/target/release/bundle/msi/` |
| 🍎 **macOS** | `.dmg`, `.app` | `src-tauri/target/release/bundle/dmg/` |
| 🐧 **Linux** | `.AppImage`, `.deb` | `src-tauri/target/release/bundle/appimage/` |

# Architecture
┌─────────────────────────────────────────────┐
│                 Tauri Shell                   │
│  ┌─────────────────┬───────────────────────┐ │
│  │   Rust Backend   │    React Frontend     │ │
│  │                  │                       │ │
│  │  ┌────────────┐  │  ┌─────────────────┐ │ │
│  │  │ Rope Engine│  │  │  Editor Panel   │ │ │
│  │  │  (ropey)   │◄─┼──│  (CodeMirror)   │ │ │
│  │  └────────────┘  │  └─────────────────┘ │ │
│  │                  │          ▲▼           │ │
│  │  ┌────────────┐  │  ┌─────────────────┐ │ │
│  │  │ Git Cmds   │  │  │ Live Preview    │ │ │
│  │  │ (process)  │◄─┼──│ (iframe sync)   │ │ │
│  │  └────────────┘  │  └─────────────────┘ │ │
│  │                  │                       │ │
│  │  ┌────────────┐  │  ┌─────────────────┐ │ │
│  │  │ LSP Client │  │  │ Command Palette │ │ │
│  │  │ (stdio)    │◄─┼──│ (Ctrl+Shift+P)  │ │ │
│  │  └────────────┘  │  └─────────────────┘ │ │
│  │                  │                       │ │
│  │  ┌────────────┐  │  ┌─────────────────┐ │ │
│  │  │File Manager│  │  │  File Explorer  │ │ │
│  │  │ (fs ops)   │◄─┼──│  (tree view)    │ │ │
│  │  └────────────┘  │  └─────────────────┘ │ │
│  └─────────────────┴───────────────────────┘ │
└─────────────────────────────────────────────┘

# Keyboard Shortcuts

| Atajo (Shortcut) | Acción |
| :--- | :--- |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> | 🎨 Command Palette |
| <kbd>Ctrl</kbd> + <kbd>O</kbd> | 📂 Open File |
| <kbd>Ctrl</kbd> + <kbd>S</kbd> | 💾 Save File |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd> | 🗄️ Save All |
| <kbd>Ctrl</kbd> + <kbd>N</kbd> | 📄 New File |
| <kbd>Ctrl</kbd> + <kbd>B</kbd> | 🛠️ Toggle Sidebar |
| <kbd>Ctrl</kbd> + <kbd>J</kbd> | 👁️ Toggle Preview |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>G</kbd> | 🌿 Git Panel |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>I</kbd> | 🔍 Layout Inspector |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>M</kbd> | 🖼️ Stock Image Search |
| <kbd>Ctrl</kbd> + <kbd>`</kbd> | 💻 Toggle Terminal |

# 🤝 Contributing

We welcome contributions! **LCE** is built by the community, for the community.

### 🚀 Getting Started


| Step | Action | Command / Detail |
| :--- | :--- | :--- |
| 1️⃣ | **Fork** | Fork this repository to your account |
| 2️⃣ | **Branch** | `git checkout -b feature/amazing-feature` |
| 3️⃣ | **Code** | Follow our style guide (see below) |
| 4️⃣ | **Test** | `cargo test && cd src-ui && npm test` |
| 5️⃣ | **Commit** | Use [Conventional Commits](https://www.conventionalcommits.org) |
| 6️⃣ | **Push** | `git push origin feature/amazing-feature` |
| 7️⃣ | **PR** | Open a Pull Request for review |

---

> [!IMPORTANT]
> From **Angel Nerozzi** with ❤️ to all developers around the world.

# 🛠️ Code Style

| Language / Tool | Standards |
| :--- | :--- |
| 🦀 **Rust** | `rustfmt` defaults + `cargo clippy` (Zero warnings) |
| 🟦 **TypeScript** | ESLint + Prettier (Strict mode enabled) |
| 📝 **Commits** | [Conventional Commits](https://www.conventionalcommits.org) |
| 📥 **PRs** | Include screenshots for UI changes |

---

# 🎯 Project Priorities

*   **🏎️ Performance** — Never regress on memory or startup time.
*   **🎯 Simplicity** — If it needs a tutorial, redesign it.
*   **♿ Accessibility** — Full keyboard navigation, screen reader support.
*   **🖤 Monochrome** — No color in chrome. Only in code.

# ⚖️ License

**MIT License** — See [LICENSE](LICENSE) for details.

---

<div align="center">

### Built with obsessive minimalism.
*Less interface. More code.*

**❤️ to all developers around the world.**

</div>

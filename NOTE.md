### 1. Prerequisites

  ApiArk is a monorepo built with Tauri v2 (Rust backend + React 19/Vite frontend). You will need:

  1. Bun (>= 1.1.0):
    curl -fsSL https://bun.sh/install | bash

  2. Rust & Cargo (Stable toolchain):
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

  3. OS System Dependencies (for Tauri v2):
      • macOS: Xcode Command Line Tools:
        xcode-select --install

      • Linux (Ubuntu/Debian):
        sudo apt-get update && sudo apt-get install -y libwebkit2gtk-4.1-dev libappindicator3-dev librsvg2-dev patchelf

      • Windows: Microsoft C++ Build Tools https://visualstudio.microsoft.com/visual-cpp-build-tools/ and WebView2.

  ──────
  ### 2. Install Dependencies

  In the root of the repository:

    bun install
  ──────
  ### 3. Run the App

  Depending on what part of the project you want to run:

  #### Option A: Full Desktop Application (Recommended)

  Launches the native desktop window connected to the Vite frontend and Rust backend with hot reloading:

    bun run tauri dev

  (Note: On the first run, Cargo will download and compile the Rust crates, which takes 2–5 minutes).

  #### Option B: Frontend Only (Browser Preview)

	If you only want to quickly inspect or tweak UI components without compiling Rust:

    bun run dev

  Accessible at http://localhost:1420. (Backend Tauri IPC commands will be unavailable in a standard browser).

  #### Option C: CLI Tool

  If you want to run the Rust CLI (apiark):

    cd apps/cli
    cargo run -- --help

  #### Option D: Web / Marketing Site

  If you want to run the Next.js landing site:

    bun --filter @apiark/web dev

  Accessible at http://localhost:3000.
  ──────
  ### 4. Useful Validation & Build Commands

  • Typecheck: bun run typecheck
  • Frontend Tests: bun run test
  • Lint: bun run lint
  • Build Production Desktop App: bun run tauri build

  ### Key Reference Files

  • README.md:145-155 — Overview and build instructions
  • package.json:6-14 — Workspace npm/bun scripts
  • apps/desktop/src-tauri/tauri.conf.json — Tauri configuration

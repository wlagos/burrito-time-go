# Burrito Time Go — Tauri Desktop Wrapper

A native desktop app wrapper for [Burrito Time Go](https://burrito-time-go.base44.app), built with [Tauri v2](https://tauri.app).

---

## Prerequisites

### 1. Rust
Install Rust via [rustup](https://rustup.rs/):
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

### 2. System dependencies

**macOS:**
```bash
xcode-select --install
```

**Ubuntu/Debian:**
```bash
sudo apt update
sudo apt install libwebkit2gtk-4.1-dev libappindicator3-dev librsvg2-dev patchelf
```

**Windows:**
- Install [Microsoft C++ Build Tools](https://visualstudio.microsoft.com/visual-cpp-build-tools/)
- Install [WebView2](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) (usually pre-installed on Windows 11)

### 3. Node.js
Install Node.js v18+ from [nodejs.org](https://nodejs.org/).

---

## Setup

```bash
# Install JS dependencies
npm install
```

---

## Development

Launches the app pointing at the live base44 URL:

```bash
npm run dev
```

---

## Build (Production)

Produces a native installer for your platform:

```bash
npm run build
```

Output binaries will be in `src-tauri/target/release/bundle/`.

---

## App Icon

Replace the placeholder files in `src-tauri/icons/` with your own icons:

| File | Size |
|------|------|
| `32x32.png` | 32×32 |
| `128x128.png` | 128×128 |
| `128x128@2x.png` | 256×256 |
| `icon.icns` | macOS icon bundle |
| `icon.ico` | Windows icon |

You can generate all sizes automatically using:
```bash
npx tauri icon path/to/your/icon.png
```

---

## Project Structure

```
tauri-base44-wrapper/
├── package.json               # JS deps & npm scripts
├── README.md
└── src-tauri/
    ├── tauri.conf.json         # Tauri config (URL, window size, etc.)
    ├── Cargo.toml              # Rust dependencies
    ├── build.rs                # Tauri build script
    ├── icons/                  # App icons (replace with your own)
    ├── capabilities/
    │   └── default.json        # Tauri v2 permissions
    └── src/
        ├── main.rs             # Rust entry point
        └── lib.rs              # App logic
```

---

## Customization

To point this wrapper at a different base44 app, update the `url` and `devUrl` fields in `src-tauri/tauri.conf.json`:

```json
"devUrl": "https://your-app.base44.app",
...
"url": "https://your-app.base44.app"
```

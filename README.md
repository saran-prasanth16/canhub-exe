# CANHub AIPass — Windows Desktop App

Native Windows wrapper for **[canhub-aipass.in](https://canhub-aipass.in)**, built with [Pake](https://github.com/tw93/Pake) (Rust + Tauri). The full website experience in a lightweight 11 MB desktop app — no browser tabs, no Electron.

## ⬇️ Download

**[Download CANHub-AIPass.exe](./CANHub-AIPass.exe)** — or open [`index.html`](./index.html) for the styled download page.

| | |
|---|---|
| Platform | Windows 10 / 11 (x64) |
| Size | ~11 MB |
| Runtime | WebView2 (pre-installed on Windows 11) |
| Version | 1.0.0 |

> **SmartScreen note:** the app is unsigned. If Windows shows a warning, click **More info → Run anyway**.

## 🔧 Rebuild it yourself

This repo includes a GitHub Actions workflow that builds the official **NSIS installer** on real Windows runners:

1. Go to the **Actions** tab
2. Select **Build CANHub-AIPass Windows App**
3. Click **Run workflow**
4. Download the artifact when the run finishes (setup `.exe` + portable binary)

## 🛠 How it was built

- [Pake](https://github.com/tw93/Pake) wraps the website into a native window using the system WebView
- This portable `exe` was cross-compiled from Linux via `cargo-xwin` (Windows SDK + MSVC target, no Windows machine needed)
- The NSIS installer variant is produced by the included workflow on `windows-latest`

## 📁 Repo layout

```
├── index.html                        # styled download page (host on GitHub Pages)
├── CANHub-AIPass.exe                 # portable Windows app
└── .github/workflows/
    └── build-canhub-windows.yml      # one-click installer build
```

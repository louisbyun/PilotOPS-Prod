# Installing PilotOPS™

> **Pre-release notice:** Installer downloads aren't yet published. This guide describes the install experience you'll have once v1.0 ships.

---

## Windows

PilotOPS™ for Windows ships as an unsigned `.exe` / `.msi` for now. This is normal for indie software and the warnings are easy to bypass — but they can be a little intimidating the first time. Here's exactly what you'll see and how to proceed.

### Step 1 — Browser download warning

When you download from this repo, your browser may show:

> **"This file isn't commonly downloaded"** (Chrome / Edge)

→ Click **Keep** (Chrome) or **Keep anyway** (Edge). The file is safe — your browser is just being cautious because PilotOPS is new.

### Step 2 — Windows SmartScreen warning

When you double-click the installer, Windows displays a full-screen blue overlay:

> **"Windows protected your PC"**
> Microsoft Defender SmartScreen prevented an unrecognized app from starting.

The default screen shows only **Don't run**. To proceed:

1. Click **More info** (small text, top-left of the dialog)
2. A new button appears: **Run anyway**
3. Click **Run anyway**

That's it — the installer will launch normally.

### Step 3 — First launch

After installation, the first time you launch PilotOPS™ you may see SmartScreen one more time. Same fix: **More info → Run anyway**. Subsequent launches won't show any warning.

### Step 4 — Antivirus (rare)

Windows Defender almost always passes PilotOPS without complaint. Some third-party AV (Avast, AVG, McAfee) occasionally false-positive on unsigned apps. If your AV quarantines PilotOPS:

1. Open your AV's quarantine / threat history
2. Restore PilotOPS and add it to the allowlist / exceptions
3. Re-run the installer

If that doesn't work, [open an issue](https://github.com/louisbyun/PilotOPS-Prod/issues) — we'll help.

### Why no certificate?

Code-signing certificates for Windows cost $300-400/year. As an indie one-person shop, we're holding off until enough customers have purchased to justify it. Every extra dollar saved goes into making the product better, not into Sectigo's pockets.

We'll add Microsoft-trusted code signing once we hit a sustainable sales volume — at which point all of this becomes unnecessary.

---

## macOS

PilotOPS™ for macOS is **signed with an Apple Developer ID** and **notarized by Apple**. This means it runs without any scary warnings — just open the `.dmg`, drag PilotOPS to Applications, and launch.

Universal binary (Apple Silicon + Intel) supported.

---

## Linux

PilotOPS™ for Linux ships as `.AppImage` (and `.deb` for Debian/Ubuntu). No signing, no installer — just download, `chmod +x`, and run.

```bash
chmod +x PilotOPS_x64.AppImage
./PilotOPS_x64.AppImage
```

Or for `.deb`:

```bash
sudo dpkg -i pilotops_x64.deb
```

---

## Verifying integrity (all platforms)

Each release includes SHA256 hashes of all installer files (in the GitHub Release notes). To verify a download wasn't tampered with:

**Windows (PowerShell):**
```powershell
Get-FileHash -Algorithm SHA256 PilotOPS_x64.msi
```

**macOS / Linux:**
```bash
shasum -a 256 PilotOPS_x64.dmg
```

Compare the output to the hash published on the [release page](https://github.com/louisbyun/PilotOPS-Prod/releases).

---

## Need help?

- **Bug or install issue:** [open an issue](https://github.com/louisbyun/PilotOPS-Prod/issues)
- **General questions:** aiswingx.com@gmail.com
- **Inside the app:** **Contact** tab — sends straight to the developer

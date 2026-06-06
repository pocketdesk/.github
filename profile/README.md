# pocketdesk

**A pocket-sized Linux dev workstation — your phone is the computer, AR glasses are the screen, a folding keyboard is the input. No laptop.**

📖 **Docs & guides → https://pocketdesk.github.io/**

---

## What is this?

pocketdesk documents a fully mobile development setup: write code in **VS Code on
Linux (Debian / Wayland)** running **directly on a Pixel phone**, displayed on **AR
glasses**, driven by a **folding Bluetooth keyboard with trackpad**. Train, plane tray
table, or café — a real desktop, in your pocket.

```
Pixel 10 Pro XL (today) / 11 Pro XL (tomorrow)
  ├─ AR glasses          → USB-C DisplayPort → virtual 1200p screen
  ├─ Folding BT keyboard → paired in Android → keyboard + trackpad
  └─ Android Linux Terminal (Debian VM, AVF/KVM)
       └─ labwc + VS Code (Wayland)   ·   fallback: code-server in the browser
```

## Why it works

Three recent pieces line up:

1. **Android's Linux Terminal** (Android 16+) runs a full **Debian VM** via the Android
   Virtualization Framework. On Pixel it includes **GPU-accelerated GUI apps** — a real
   VS Code window, not just a shell.
2. **USB-C DisplayPort Alt Mode** lets the phone drive an external display — the AR
   glasses are just a wearable monitor.
3. **Bluetooth HID** keyboard/mouse pair at the **Android** level and are forwarded into
   the Linux VM — nothing to configure inside Debian.

## Reference hardware

| Part | Reference | Notes |
|---|---|---|
| **Phone** | Pixel 10 Pro XL *(today)* → 11 Pro XL *(≈ Sep 2026)* | Pixel for the GPU-accelerated Linux GUI; model-agnostic chain |
| **Glasses** | XReal 1S · Viture Luma Ultra · Viture Beast | XReal X1 = built-in spatial/ultrawide (no app); Viture = SpaceWalker for multi-screen (Luma Ultra adds 6DoF/depth cameras) |
| **Keyboard** | ProtoArc XK01 TP (AZERTY) | Tri-fold, full layout + integrated trackpad |

> **Model-agnostic.** The software chain depends on **Android + AVF**, not a specific
> phone — every guide works on the Pixel 10 Pro XL today and transposes unchanged to the
> 11 Pro XL at launch.

## Repositories

- [`pocketdesk.github.io`](https://github.com/pocketdesk/pocketdesk.github.io) — the
  documentation site (Hugo).
- [`docs`](https://github.com/pocketdesk/docs) — source notes / drafts.

## Status & disclaimer

Community knowledge base — **not affiliated** with Google, Viture, or XREAL.
Pre-release device specs (e.g. Pixel 11 Pro XL) are **leaks** and must be re-confirmed
at launch. Everything moves fast across Android 16/17 — re-verify after major updates.

# Kayden D'Mello

Creator of **[Tesserae](https://tesserae.ink)** — an open-source platform for e-paper dashboards.
I build Python backends, embedded firmware, native macOS applications, and developer tooling.

Melbourne, Australia · Ex-ANZ (platform engineering & automation) · Open to full-stack, platform, and embedded-adjacent roles.

[dmello.io](https://dmello.io) · [LinkedIn](https://www.linkedin.com/in/dmello-io/) · dmellok@icloud.com

---

## Tesserae

**[tesserae.ink](https://tesserae.ink)** · **[Documentation](https://docs.tesserae.ink/)** · **[Source](https://github.com/dmellok/tesserae)**

A self-hosted dashboard server for e-ink displays. Compose tile-based dashboards in the browser; the server renders them headless, dithers against each panel's *measured* colour palette, packs the frame into the panel's native byte format, and delivers it over MQTT (always-on clients) or REST (battery clients). One server drives a fleet of panels — Raspberry Pi, ESP32, Kindle, TRMNL-compatible — with 14 panels verified on real hardware.

AGPL-3.0-or-later. No cloud account, no hosted version — you run it.

```
browser editor           Tesserae server                     panels
┌──────────┐   HTTP   ┌──────────────────────┐  MQTT push  ┌─────────────┐
│ composer │─────────▶│ headless render      │────────────▶│ Pi + Inky   │
│ /compose │          │ dither (measured     │             ├─────────────┤
└──────────┘          │   palettes)          │  REST pull  │ ESP32,      │
                      │ pack panel-native    │◀───────────▶│ Kindle,     │
                      │ schedule / rotate    │             │ TRMNL       │
                      └──────────────────────┘             └─────────────┘
```

**What makes it interesting**

- **Render once, correctly.** The editor preview and the production render load the same URL in headless Chromium, so a dashboard can't look right in the editor and break on the panel.
- **Dumb firmware by design.** Devices do no on-device image decoding — the server ships exact panel-native bytes (packed Spectra 6, 1-bit mono, 4-bit grayscale). Supporting a new panel is a board header plus one driver.
- **Everything is a plugin.** Widgets, themes, fonts, renderers, transports, and device kinds are drop-a-folder extension points — the seams are real directories in the repo.
- **Sandboxed third-party widgets.** Widgets declare the network hosts they need; the host enforces the allowlist at the socket layer. Community widgets install from an [audited, sha256-pinned catalog](https://github.com/dmellok/tesserae-widgets).
- **Battery-first device protocol.** ESP32 clients wake, `GET` their frame with `If-None-Match` (a 304 skips the download *and* the slow e-ink refresh), report telemetry, and deep-sleep on a server-driven interval.
- **Real installation paths.** Docker, Home Assistant add-on, LXC/Proxmox, shell installer — and ESP32 boards flash straight from the browser at [tesserae.ink/flash](https://tesserae.ink/flash), no toolchain.

Pre-1.0 and moving fast: 1,100+ tests, ruff and `mypy --strict` on every push, every release documented in the [changelog](https://github.com/dmellok/tesserae/blob/main/CHANGELOG.md).

### The ecosystem

Tesserae is split into focused repositories, each owning one layer:

| Layer | Repository | What it does |
|---|---|---|
| Core platform | [tesserae](https://github.com/dmellok/tesserae) | Server: editor, render pipeline, scheduler, plugin loader, MQTT + REST transports, docs |
| Device firmware | [tesserae-device-firmware](https://github.com/dmellok/tesserae-device-firmware) | One ESP-IDF codebase driving eight e-paper boards (Seeed reTerminal E-Series, XIAO, Waveshare, TRMNL DIY), flashable from the browser |
| Raspberry Pi clients | [tesserae-device-pi-png](https://github.com/dmellok/tesserae-device-pi-png) · [tesserae-device-pi-bin](https://github.com/dmellok/tesserae-device-pi-bin) | Daemons that paint frames onto Pimoroni Inky panels — a PNG path for the broadest hardware support, a packed-binary path for speed |
| Microcontroller client | [tesserae-device-pico-bin](https://github.com/dmellok/tesserae-device-pico-bin) | RP2350 deep-sleep client for Inky panels, written in C against the Pico SDK |
| Widget catalog | [tesserae-widgets](https://github.com/dmellok/tesserae-widgets) | Community widgets: pinned release tarballs, sha256-verified, schema-validated, PR-reviewed |
| Home Assistant | [homeassistant-tesserae-addon](https://github.com/dmellok/homeassistant-tesserae-addon) | Supervisor add-on — Tesserae in the HA sidebar, authenticated through HA's own session |

---

## Other projects

### [Claude Usage](https://github.com/dmellok/claude-usage)

Native macOS menu-bar app showing live Claude Code usage: 5-hour and 7-day windows, per-model breakdowns, and extra-usage credits, with reset countdowns in the menu bar. Built because usage limits are invisible until you hit them. Swift/SwiftUI, reads OAuth tokens from the Keychain (with refresh handling), and includes a zero-dependency MQTT 3.1.1 publisher on Apple's Network framework for Home Assistant dashboards.

### [OpenBanking Finance](https://github.com/dmellok/openbanking-finance)

Self-hosted personal finance dashboard for Australian bank and brokerage accounts via the Consumer Data Right. Built because personal financial data shouldn't live in someone else's cloud. FastAPI + SQLModel/SQLite with an in-process scheduler; the async sync client is rate-limit aware and idempotent (watermarks + merge on provider ID); money is `Decimal` end-to-end; six tabs of ECharts visualisations with no frontend build step. `mypy --strict` and pytest in CI.

### [VFD Desk HUD](https://github.com/dmellok/vfd-dash)

Custom firmware for a 256×50 vacuum-fluorescent display driven by a Raspberry Pi Pico W — eleven pages of live info (weather, now-playing with audio visualisers, 3D-print progress, Claude usage) fed over MQTT. Required a custom u8g2 fork: the GP1287BI controller isn't upstream, and the panel needs LSB-first software SPI on a non-SCK pin. OTA updates, a wireless screenshot endpoint, and Home Assistant presence/lux integration. [Build writeup](https://dmello.io/building-a-vfd-desk-hud-with-a-pi-pico-w/).

---

## Technologies

**Backend** — Python, Flask, FastAPI, SQLModel, SQLite, Playwright, pytest, ruff, mypy (strict)

**Frontend** — TypeScript, Lit, vanilla JS, Chart.js, ECharts, Astro, server-rendered HTML/CSS

**Embedded** — C, C++, ESP-IDF, Pico SDK, PlatformIO, ESP32-S3, RP2040/RP2350, e-paper and VFD drivers

**Native** — Swift, SwiftUI, Keychain, Network framework, menu-bar apps

**Infrastructure** — Docker, GitHub Actions, MQTT, Home Assistant, REST/OpenAPI, OAuth, systemd

---

## Current focus

- Growing Tesserae's hardware support — a generic CircuitPython client covering 400+ boards is [in development](https://github.com/dmellok/tesserae/discussions/24)
- Improving the render pipeline: palette calibration, dithering quality, panel-native formats
- Growing the community widget catalog and its review tooling
- Keeping the [documentation](https://docs.tesserae.ink/) ahead of the code

---

If Tesserae earns a place on your wall, [sponsorship](https://github.com/sponsors/dmellok) keeps the panels lit. For everything else: [dmello.io](https://dmello.io) · [LinkedIn](https://www.linkedin.com/in/dmello-io/) · dmellok@icloud.com

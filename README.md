### Kayden D'Mello

Melbourne-based developer building full-stack Python systems, embedded display hardware, native macOS tools, and automation platforms.

Former ANZ RPA Developer / Platform Support Engineer. Currently open to work in full-stack, automation/RPA, platform engineering, and embedded-adjacent roles.

---

#### Flagship work

[**Tesserae**](https://github.com/dmellok/tesserae)  
Self-hosted dashboard companion for e-ink panels. Compose dashboards in a browser, render them server-side, and push frames to Raspberry Pi, ESP32, Pico, Kindle, TRMNL-style, and other panels over MQTT/HTTP. Tesserae is my main open-source project: server, plugin system, device clients, Home Assistant integration, widget marketplace, docs, installers, tests, and hardware support.

[**VFD Desk HUD**](https://github.com/dmellok/vfd-dash)  
Pi Pico W firmware for a 256×50 GP1287BI vacuum-fluorescent desk display. MQTT-fed live pages, OTA flashing, Home Assistant presence/lux integration, and a custom u8g2 fork for the BI controller. [Build writeup](https://dmello.io/building-a-vfd-desk-hud-with-a-pi-pico-w/?ref=github).

[**OpenBanking Finance**](https://github.com/dmellok/openbanking-finance)  
Self-hosted FastAPI dashboard for Australian CDR banking and brokerage data. Async Redbark ingestion, SQLModel persistence, Decimal-safe money handling, rate-limit-aware sync, and chart-heavy personal finance views.

[**Claude Usage**](https://github.com/dmellok/claude-usage)  
Native macOS menu-bar app for Claude Code usage tracking. Swift/SwiftUI app that reads OAuth credentials from Keychain, calls Anthropic usage endpoints, and publishes usage data to MQTT for Home Assistant or external dashboards.

---

#### Tesserae ecosystem

Tesserae is split into focused repositories rather than one monolith:

- [**tesserae**](https://github.com/dmellok/tesserae) — core Flask server, editor, renderer pipeline, scheduler, MQTT/HTTP transport, plugin loader, widget runtime, theme system, installers, and docs.
- [**tesserae-widgets**](https://github.com/dmellok/tesserae-widgets) — community widget catalog, screenshots, manifests, and audit-oriented review flow.
- [**homeassistant-tesserae-addon**](https://github.com/dmellok/homeassistant-tesserae-addon) — Home Assistant Supervisor add-on packaging.
- [**tesserae-device-pi-png**](https://github.com/dmellok/tesserae-device-pi-png) / [**tesserae-device-pi-bin**](https://github.com/dmellok/tesserae-device-pi-bin) — Raspberry Pi panel clients.
- [**tesserae-device-esp32-bin**](https://github.com/dmellok/tesserae-device-esp32-bin) / [**tesserae-device-esp32-bw**](https://github.com/dmellok/tesserae-device-esp32-bw) — ESP32 e-paper firmware clients.
- [**tesserae-device-pico-bin**](https://github.com/dmellok/tesserae-device-pico-bin) — RP2350/Pico-class e-paper client.
- [**Tesserae topic view**](https://github.com/dmellok?tab=repositories&q=topic%3Atesserae) — widget bundles, theme packs, device clients, and experiments.

Representative widgets include calendar/schedule, recipes, Spotify, GitHub, PostHog, finance, AFL/F1/football, Melbourne transport, BoM warnings, sky/aurora, OpenSky flights, Glances, OctoPrint, public-domain art, iCloud Shared Albums, Unsplash, and AI-generated briefs.

---

#### What I’m good at

- Turning messy integrations into coherent, documented, shippable systems.
- Python services with real test suites, CI, installers, release notes, and operational polish.
- Hardware-adjacent software: MQTT, OTA, display drivers, render pipelines, battery-aware clients, and Home Assistant integration.
- Native macOS utilities in Swift/SwiftUI with secure credential handling.
- Automation and platform support shaped by production RPA experience.
- Building small tools that connect APIs, dashboards, hardware, and local infrastructure.

---

#### Stack

**Backend**  
Python · Flask · FastAPI · SQLModel · SQLite · Playwright · pytest · ruff · mypy

**Frontend / UI**  
TypeScript · Lit · vanilla JavaScript · Chart.js · server-rendered HTML/CSS

**Native**  
Swift · SwiftUI · macOS menu-bar apps · Keychain

**Embedded / hardware**  
C · C++ · ESP32-S3 · RP2040/RP2350 · Raspberry Pi · PlatformIO · ESP-IDF · arduino-pico · e-paper · VFDs

**Systems / integration**  
MQTT · Docker · Home Assistant · GitHub Actions · REST APIs · OAuth · webhooks · local-first tooling

**AI / automation**  
Anthropic API · Claude Code · MCP · workflow automation · RPA/platform operations

---

#### Current focus

I’m currently focused on Tesserae: making e-ink dashboards easier to install, extend, and run across real hardware. The project touches most of the work I enjoy: backend architecture, plugin systems, render pipelines, embedded clients, MQTT, Home Assistant, docs, release engineering, and product polish.

---

#### Reach me

[dmello.io](https://dmello.io/?ref=github) · [LinkedIn](https://www.linkedin.com/in/dmello-io/) · dmellok@icloud.com

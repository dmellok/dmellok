### Kayden D'Mello

Developer in Melbourne. Twelve years at ANZ, the last six as an RPA Developer / Platform Support Engineer (until December 2025). Now I ship full-stack Python services, native macOS in Swift, and embedded C/C++ on RP2040 and ESP32-S3, usually with each other on the other end of an MQTT topic.

**Currently open to work**: full-stack, automation/RPA, embedded-adjacent.

---

#### What I'm working on

[**Tesserae**](https://github.com/dmellok/tesserae): composable e-ink dashboard platform. Plugin-architected renderers and devices, 33 bundled widgets plus a [community catalog](https://github.com/dmellok/tesserae-widgets) of opt-in bundles, MQTT auto-discovery across multiple panels, Docker + bare-metal installers, [docs site](https://dmellok.github.io/tesserae/). My main project; the full ecosystem is grouped below.

[**OpenBanking Finance**](https://github.com/dmellok/openbanking-finance): self-hosted FastAPI dashboard ingesting Australian CDR transactions via Redbark. SQLModel persistence, rate-limit-aware async client, Decimal-precision money, six tabs of charts.

[**Claude Usage**](https://github.com/dmellok/claude-usage): native macOS menu-bar app for Claude Code budgets. Reads the OAuth token from Keychain, calls Anthropic's usage endpoint, publishes the result to MQTT for Home Assistant.

[**VFD Desk HUD**](https://github.com/dmellok/vfd-dash): Pi Pico W driving a 256×50 GP1287BI vacuum-fluorescent panel. 11 pages, OTA flashing, custom u8g2 fork for the BI controller, ~20 fps render loop. [Full writeup](https://dmello.io/building-a-vfd-desk-hud-with-a-pi-pico-w/?ref=github).

---

#### Tesserae ecosystem

<details>
<summary><b>Core</b> · 3 repos</summary>

- [tesserae](https://github.com/dmellok/tesserae) · the server: composer, renderers, scheduler, MQTT push, Spectra theme system, marketplace install pipeline
- [tesserae-widgets](https://github.com/dmellok/tesserae-widgets) · the community catalog index + screenshots, audit-only review
- [homeassistant-tesserae-addon](https://github.com/dmellok/homeassistant-tesserae-addon) · HA Supervisor App (stable + edge channels)

</details>

<details>
<summary><b>Clients</b> · 6 repos · daemons + firmware that paint a panel</summary>

- [tesserae-device-pi-png](https://github.com/dmellok/tesserae-device-pi-png) · Raspberry Pi, universal PNG path via the Pimoroni `inky` library
- [tesserae-device-pi-bin](https://github.com/dmellok/tesserae-device-pi-bin) · Raspberry Pi, fast 4-bpp `.bin` path for Inky Impression
- [tesserae-device-esp32-bin](https://github.com/dmellok/tesserae-device-esp32-bin) · Battery ESP32-S3 + Waveshare 13.3" Spectra 6
- [tesserae-device-esp32-bw](https://github.com/dmellok/tesserae-device-esp32-bw) · Battery ESP32 + Waveshare 4.2" e-paper (400×300, 1-bpp B/W)
- [tesserae-device-photopainter-7.3-bin](https://github.com/dmellok/tesserae-device-photopainter-7.3-bin) · Battery ESP32-S3 + Waveshare 7.3" Spectra 6 (PhotoPainter)
- [tesserae-device-pico-bin](https://github.com/dmellok/tesserae-device-pico-bin) · Battery Pico Plus 2 (RP2350) + Pimoroni Inky Impression 13.3" Spectra 6

</details>

<details>
<summary><b>Widget bundles</b> · 25 repos · install via Browse community widgets</summary>

- [tesserae-widget-ai-brief](https://github.com/dmellok/tesserae-widget-ai-brief) · AI-generated daily brief from weather, todos, calendar, HA entities
- [tesserae-widget-recipes](https://github.com/dmellok/tesserae-widget-recipes) · Schema.org Recipe scraper (RecipeTin Eats, BBC Good Food, NYT Cooking)
- [tesserae-widget-calendar-schedule](https://github.com/dmellok/tesserae-widget-calendar-schedule) · Google-Calendar-style agenda view, multi-feed
- [tesserae-widget-paperlesspaper-art](https://github.com/dmellok/tesserae-widget-paperlesspaper-art) · Full-bleed public-domain + CC art
- [tesserae-fal-image](https://github.com/dmellok/tesserae-fal-image) · Full-bleed AI-generated images via Fal.ai (Flux Schnell, Flux Dev)
- [tesserae-widget-f1](https://github.com/dmellok/tesserae-widget-f1) · Formula 1 race weekend + standings
- [tesserae-widget-afl](https://github.com/dmellok/tesserae-widget-afl) · AFL ladder, fixtures, next/last match (Squiggle API)
- [tesserae-widget-football](https://github.com/dmellok/tesserae-widget-football) · Per-team match (next/last/live), league + group standings
- [tesserae-widget-spotify](https://github.com/dmellok/tesserae-widget-spotify) · Now playing, queue, album art
- [tesserae-widget-github](https://github.com/dmellok/tesserae-widget-github) · CI status, PR queue, contributions, releases
- [tesserae-widget-posthog](https://github.com/dmellok/tesserae-widget-posthog) · Configurable PostHog trends metric (hero number + sparkline/bar)
- [tesserae-widget-finance](https://github.com/dmellok/tesserae-widget-finance) · FX, stock, crypto
- [tesserae-widget-sky](https://github.com/dmellok/tesserae-widget-sky) · Aurora alerts + moon phase
- [tesserae-widget-bom-warnings](https://github.com/dmellok/tesserae-widget-bom-warnings) · Australian BoM weather warnings by state
- [tesserae-widget-air-traffic](https://github.com/dmellok/tesserae-widget-air-traffic) · Flights overhead via OpenSky Network
- [tesserae-widget-weather-extras](https://github.com/dmellok/tesserae-widget-weather-extras) · Air quality, pollen, wind
- [tesserae-widget-clock-extras](https://github.com/dmellok/tesserae-widget-clock-extras) · QLOCKTWO-style word clock, world clocks
- [tesserae-widget-glances](https://github.com/dmellok/tesserae-widget-glances) · Homelab host stats from a Glances API
- [tesserae-widget-octoprint](https://github.com/dmellok/tesserae-widget-octoprint) · OctoPrint 3D printer status
- [tesserae-widget-unsplash](https://github.com/dmellok/tesserae-widget-unsplash) · Daily Unsplash photo
- [tesserae-widget-apple-album](https://github.com/dmellok/tesserae-widget-apple-album) · iCloud Shared Album carousel
- [tesserae-widget-transport](https://github.com/dmellok/tesserae-widget-transport) · Melbourne PTV next departures
- [tesserae-widget-public-holiday-countdown](https://github.com/dmellok/tesserae-widget-public-holiday-countdown) · Countdown to the next public holiday
- [tesserae-widget-community-demo](https://github.com/dmellok/tesserae-widget-community-demo) · Hello-world widget for the marketplace install pipeline
- [tesserae-widget-devref](https://github.com/dmellok/tesserae-widget-devref) · Every plugin contract surface in one repo, for widget developers

Or filter the lot on the [topic page](https://github.com/dmellok?tab=repositories&q=topic%3Atesserae).

</details>

<details>
<summary><b>Theme packs</b> · 6 repos · install via Browse community widgets</summary>

- [tesserae-theme-tonal](https://github.com/dmellok/tesserae-theme-tonal) · 6 medium-vivid feature-colour-led light themes
- [tesserae-theme-pigment](https://github.com/dmellok/tesserae-theme-pigment) · 10 saturated feature-colour-led light themes
- [tesserae-theme-muted](https://github.com/dmellok/tesserae-theme-muted) · 10 mid-tone coloured-canvas themes
- [tesserae-theme-vivid](https://github.com/dmellok/tesserae-theme-vivid) · 15 saturated single-colour themes
- [tesserae-theme-gradient](https://github.com/dmellok/tesserae-theme-gradient) · 14 linear-gradient surface themes
- [tesserae-theme-auroras](https://github.com/dmellok/tesserae-theme-auroras) · 6 atmospheric aurora-inspired three-stop gradient themes

</details>

---

#### Stack

**Daily** Python · Swift · C/C++ · TypeScript · MQTT
**Web** FastAPI · Flask · SQLModel · Lit · Playwright
**Native / embedded** SwiftUI · PlatformIO · arduino-pico · ESP-IDF
**AI** Anthropic API · Claude Code · MCP

---

#### Reach me

[dmello.io](https://dmello.io/?ref=github) · [LinkedIn](https://www.linkedin.com/in/dmello-io/) · <dmellok@icloud.com>

# Amazon Price History Tracker

Track historical prices, detect discounts, and trigger instant alerts across regions and stores — all automated on Android devices and emulators. This Amazon Price History Tracker eliminates manual checks, builds a reliable time series per ASIN, and pushes alerts to Slack/Discord/Webhooks so you can act faster and price smarter.

<p align="center">
  <a href="https://Appilot.app" target="_blank"><img src="media/appilot-baner.png" alt="Appilot Banner" width="100%"></a>
</p>
<p align="center">
 <a href="https://t.me/devpilot1" target="_blank"><img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram"></a>
 <a href="mailto:support@appilot.app" target="_blank"><img src="https://img.shields.io/badge/Email-support@appilot.app-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail"></a>
 <a href="https://appilot.app" target="_blank"><img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website"></a>
 <a href="https://discord.gg/r5sJ5vhf" target="_blank"><img src="https://img.shields.io/badge/Join-Appilot_Community-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Appilot Discord"></a>
</p>

<p align="center"> 
   Created by Appilot, built to showcase our approach to Automation!<br>
   <strong>If you are looking for custom Amazon Price History Tracker, you've just found your team — Let’s Chat.👆👆</strong>
</p>

## Introduction
This system continuously monitors Amazon product pages (ASINs) on Android devices/emulators, records price changes, and aggregates a clean historical dataset. It automates repetitive visit–capture–validate cycles, prevents stale data, and notifies you the moment thresholds are met. The outcome is simple: dependable pricing intelligence you can plug into dashboards, sheets, or internal tools.

### Automating Amazon Price Intelligence & Alerts
- Captures list price, deal price, coupon presence, shipping costs, and Buy Box signals on a schedule.
- Region-aware monitoring with proxy rotation to compare marketplaces and geo-specific price variations.
- Clean, deduplicated time series stored in JSON/CSV/DB with retention and rollups.
- Real-time alerting to Slack/Discord/Webhook with configurable thresholds and diffs.
- Built for scale: parallel device execution, watchdogs, and robust retry logic.

## Core Features
- **Real Devices and Emulators:** Run on physical Android phones, device farms, or emulators (Bluestacks/Nox). Ensures parity with real user flows and renders dynamic price widgets accurately.
- **No-ADB Wireless Automation:** ADB-less control layer for stealthy, cable-free orchestration; trigger tasks over Wi-Fi with encrypted channels and reduced detection surface.
- **Mimicking Human Behavior:** Randomized delays, scroll depth variance, viewport jitter, and back/forward navigation patterns to resemble real users and stabilize render timing.
- **Multiple Accounts Support:** Rotate signed-in buyer accounts when needed for region-locked data, Prime price views, or coupon visibility checks.
- **Multi-Device Integration:** Horizontal scaling across 10–1000 devices with sharded watchlists and coordinated schedulers.
- **Exponential Growth for Your Account:** Convert pricing insights into growth—optimize buy windows, reprice inventory, and increase conversion during deal cycles.
- **Premium Support:** Priority onboarding, architecture reviews, and hands-on scaling assistance from Appilot engineers.

## Additional Feature Set
| Feature | Description |
|---|---|
| **Smart Price Diff Alerts** | Threshold- and percentage-based notifications with before/after snapshots and deep links. |
| **Historical Charting API** | Serve price timelines as JSON endpoints consumable by Grafana/Metabase dashboards. |
| **ASIN & Keyword Watchlists** | Import ASINs or auto-discover via keyword+category; de-duplicate and categorize feeds. |
| **Geo/Proxy Rotation** | Marketplace, region, and ISP diversity via rotating proxies for consistent, localized results. |
| **Sheets/CSV Sync** | Auto-export to Google Sheets/CSV on schedule with append or upsert modes. |
| **Webhooks & Integrations** | Push events to Slack/Discord/Zapier/custom webhooks for instant downstream actions. |

</p>
<p align="center">
  <a href="https://appilot.app" target="_blank">
    <img src="media/{{keyword}-banner}.png" alt="{{keyword}-architecture}" width="95%">
  </a>
</p>

## How It Works
1. **Input or Trigger** — From the Appilot dashboard, select marketplaces/regions, upload ASINs or keyword rules, set thresholds and schedules, then start a run across chosen devices/emulators.  
2. **Core Logic** — The controller orchestrates devices via **UI Automator/Appium** (or wireless control), opens product pages, waits for critical selectors, captures price, coupon, shipping, and Buy Box signals, and parses normalized fields.  
3. **Output or Action** — Results are persisted to the datastore and streamed to Sheets/CSV/Webhooks; alerts fire on diffs or threshold matches with context (previous price, delta, timestamp, device, region).  
4. **Other functionalities** — Retries with backoff, screenshot logging, device health checks, structured logs, and parallel shards ensure resilience; failures surface in the dashboard with actionable diagnostics.

## Tech Stack 
- **Language:** Kotlin, Java, JavaScript, Python  
- **Frameworks:** Appium, UI Automator, Espresso, Robot Framework, Cucumber  
- **Tools:** Appilot, Android Debug Bridge (ADB), Appium Inspector, Bluestacks, Nox Player, Scrcpy, Firebase Test Lab, MonkeyRunner, Accessibility  
- **Infrastructure:** Dockerized device farms, Cloud-based emulators, Proxy networks, Parallel Device Execution, Task Queues, Real device farm

## Directory Structure
```
amazon-price-history-tracker/
│
├── src/
│   ├── main.py
│   ├── automation/
│   │   ├── runner.py
│   │   ├── device_manager.py
│   │   ├── parsers/
│   │   │   ├── price_parser.py
│   │   │   └── coupon_parser.py
│   │   └── utils/
│   │       ├── logger.py
│   │       ├── proxy_manager.py
│   │       ├── alerting.py
│   │       └── config_loader.py
│   ├── integrators/
│   │   ├── sheets_sync.py
│   │   ├── webhook_push.py
│   │   └── charts_api.py
│   └── sched/
│       ├── scheduler.py
│       └── watchdog.py
│
├── config/
│   ├── settings.yaml
│   ├── credentials.env
│   └── devices.yaml
│
├── data/
│   ├── watchlists/
│   │   └── asin_list.csv
│   └── exports/
│       ├── prices.csv
│       └── prices.json
│
├── logs/
│   ├── runner.log
│   └── device/
│       └── device-001.log
│
├── media/
│   └── amazon-price-history-tracker-banner.png
│
├── tests/
│   ├── test_parsers.py
│   └── test_scheduler.py
│
├── docker/
│   ├── Dockerfile
│   └── docker-compose.yml
│
├── requirements.txt
└── README.md
```


## Use Cases
- **Brand owners** use it to monitor competitor price moves, so they can time promotions and protect margins.  
- **FBA sellers** use it to track Buy Box and coupon impacts, so they can optimize repricing strategies.  
- **Analysts** use it to build marketplace price indexes, so they can present weekly trends to leadership.  
- **Deal communities** use it to catch drops instantly, so they can post timely alerts and grow engagement.

## FAQs
**How do I configure this for multiple accounts?**  
Add accounts to `config/credentials.env` and map them to marketplaces in `devices.yaml`. The scheduler rotates accounts per device/marketplace and enforces cool-downs to avoid lockouts.

**Does it support proxy rotation or anti-detection?**  
Yes. Define pools in `proxy_manager.py` and policies in `settings.yaml` (per-marketplace/ISP/region). The runner randomizes headers, user flows, and pacing to reduce fingerprints.

**Can I schedule it to run periodically?**  
Use `sched/scheduler.py` to define cron-like intervals (e.g., every 15 minutes). Shards split watchlists across devices so frequent runs don’t collide.

**Where are the historical charts served?**  
`integrators/charts_api.py` exposes a lightweight HTTP endpoint returning aggregated series suitable for Grafana/Metabase or a simple web chart.

**What happens if a page layout changes?**  
Parser contracts are versioned. On selector failure, fallback heuristics and screenshots are logged; alerts notify maintainers to update parsers promptly.

## Performance & Reliability Benchmarks
- **Execution Speed:** ~1.8–3.2s DOM settle per page on warmed devices; ~120–220 ASINs/hour/device with conservative pacing.  
- **Success Rate:** **95%** successful captures on stable network and proxy pools with retries enabled.  
- **Scalability:** Proven patterns for **300–1000** Android devices via sharded queues, stateless workers, and centralized schedule/telemetry.  
- **Resource Efficiency:** Headless emulator profiles, capped FPS, and adaptive wait strategies keep CPU/RAM usage low under parallel loads.  
- **Error Handling:** Exponential backoff, circuit breakers per marketplace, structured logs, screenshot-on-failure, and alert escalation to Slack/Discord/Webhooks.


##
<p align="center">
<a href="https://cal.com/app-pilot-m8i8oo/30min" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
</p>

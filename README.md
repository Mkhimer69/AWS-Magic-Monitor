# 🚀 AWS Magic Monitor

<p align="center">
  <img src="https://img.shields.io/badge/version-3.0.0-orange?style=flat">
  <img src="https://img.shields.io/badge/platform-Amazon%20Connect%20Admin-232F3E?logo=amazonaws&logoColor=white">
  <img src="https://img.shields.io/badge/engine-Tampermonkey-00485B?style=flat">
  <img src="https://img.shields.io/badge/backend-none%20·%20fully%20client--side-success?style=flat">
  <img src="https://img.shields.io/badge/latency-real--time-red?style=flat">
</p>

> A real-time workforce command center for the **Amazon Connect admin website** —
> a Tampermonkey userscript that intercepts the Connect Analytics API live and
> turns raw agent data into a draggable, black-and-gold monitoring panel for
> RTAs, WFM, ops managers, and team leads. No external APIs, no backend, no
> databases.

> **🧭 Where it runs:** the **admin-side Amazon Connect dashboards**
> (`my.connect.aws` — Analytics / Real-time metrics, used by supervisors and
> WFM teams). This tool does **not** touch the agent workspace (CCP) — if you
> want to reskin the agent workspace, that's
> [**AWS Connect Theme Studio**](https://github.com/Mkhimer69/AWS-Connect-Theme-Studio).

## 📸 Overview

<p align="center"><img src="https://raw.githubusercontent.com/Mkhimer69/AWS-Magic-Monitor/main/assets/AWS-Magic-Monitor.png" width="800" alt="AWS Magic Monitor panel"></p>

Everything runs on data the admin dashboards already load — the script sits on
the Connect Analytics fetch calls, boosts the page size to **1000 agents per
pull**, and re-renders on every refresh without touching a server.

## ✨ Features

| Area | What you get |
|---|---|
| 🔴 **Live monitoring** | Fetch-level API interception, auto re-render on dashboard refresh, per-queue cards |
| 📊 **Queue analytics** | Occupancy % (active slots / capacity), total HC, location breakdown |
| 🟢 **Agent visibility** | Available / On Contact / Break / Lunch / Coaching chips, state durations, longest active contact per queue |
| 🚨 **Compliance flags** | Configurable thresholds, flagged agents auto-expand, per-queue flag export |
| 📋 **Routing profiles** | Distribution counts per routing profile per queue |
| ⏭️ **Next activity** | What each agent is queued to do next, grouped and sorted |
| 💾 **CSV export** | One click → `Agent_RealTime_Status.csv` of the entire pull |
| 🖱 **UI** | Draggable, resizable, collapsible panel · gold-on-black executive theme · toasts |

## 🚦 Compliance Flags

| State | Flag threshold |
|---|---|
| Break | > 16 min |
| Lunch | > 31 min |
| Coaching/Feedback | > 31 min |
| Meeting | > 31 min |
| Missed | any (> 1 s) |
| After Contact Work | > 8 min |

Flag rules are trivially editable in the source — tune them to your operation.

## ⚙️ How It Works

1. **Intercept** — the script wraps `window.fetch` and watches for Connect
   Analytics requests carrying `AGENT` + `CHANNEL` metrics.
2. **Boost** — outgoing payloads are rewritten to `pageSize: 1000` so the pull
   covers the whole floor instead of one page.
3. **Extract** — agent name, state, state duration, routing profile, group,
   next state, and active/capacity slots are parsed per row.
4. **Aggregate** — agents group by routing profile → occupancy, chips, flags,
   and profile distributions are computed per queue.
5. **Render** — queue cards update in place; data is also mirrored to
   `localStorage` for companion tooling.

## 📥 Installation

> *The distribution build is not yet published. When released, it will be a
> one-click install; steps below.*

1. Install the [Tampermonkey](https://www.tampermonkey.net/) browser extension
2. Install **AWS Magic Monitor** from the release/raw link *(coming soon)*
3. Open the **Amazon Connect admin website** (`my.connect.aws`) and open an
   analytics dashboard with real-time agent metrics — e.g. **Analytics →
   Real-time metrics** (this is the admin side, not the agent workspace)
4. The 🚀 panel appears top-left — drag it anywhere

## 🖥 Usage

- **Drag** the header to move · **− / +** collapses the panel · corner-resize
- **🔄** triggers the dashboard's own refresh for an instant re-pull
- **💾** exports the current full dataset to CSV
- **💬** on the Flags row hands that queue's flags to the companion send hook
- Expand any chip (🟢 ☕ 🍽️ 🎯 📞 🚨 📋 ⏭️) for sorted agent rows

## 👥 Who Uses It

Built for the **admin side** of Amazon Connect — supervisors, WFM and
operations teams who already live in the admin dashboards:

| Role | Value |
|---|---|
| Real-Time Analysts | Occupancy & staffing state across all queues at a glance |
| Workforce Management | Routing profile trends, staffing imbalances, CSV for planning |
| Operations Managers | Live queue health and compliance risk without opening six tabs |
| Team Leads | Individual agent status and flag follow-ups |

## 🔮 Roadmap

- **v3.1** — queue filters · queue search · longest-available tracking
- **v3.2** — queue health indicators · staffing-risk detection · occupancy threshold alerts
- **v4.0** — screenshot mode · alert center · historical snapshots & trend analysis

## 🛠 Technology

JavaScript · Tampermonkey · Amazon Connect Analytics (admin dashboards) · fetch interception · HTML/CSS — 100% client-side.

## 🔒 Confidentiality Notice

The distribution build is currently private while internal thresholds and
routing structures are sanitized. This repository documents the tool's
capabilities, architecture, and roadmap — no production data, credentials, or
company-sensitive logic is included.

---

<div align="center">
<b>🚀 AWS Magic Monitor</b><br><i>Your whole floor. One panel. Zero backend.</i>
</div>

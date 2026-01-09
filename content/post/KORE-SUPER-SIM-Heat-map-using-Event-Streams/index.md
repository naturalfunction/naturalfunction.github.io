---
title: "Build a Real-Time IoT Heatmap with KORE SUPER SIM Event Streams"
date: 2025-11-26
description: "Build a real-time geospatial dashboard for KORE SUPER SIM using Event Streams, FastAPI, and Leaflet. Complete GitHub code and tutorial for IoT visualization."
categories: ["KORE", "API", "Event Streams", "GitHub Code"]
tags: ["SUPER SIM", "KORE ONE", "Cellular Connectivity", "Python"]
image: "heatmap-cover.png"
---

![KORE SUPER SIM logo](KORE-LOGO-SUPERSIM.png)

# Visualizing KORE SUPER SIM Event Streams in Real Time

Hi there, my name is **Vitor Ribeiro**, and I am a **Solutions Architect** at **KORE Wireless**.

In this article, I’ll show you how I built a full real-time geospatial visualization tool for [**KORE SUPER SIM**](https://www.korewireless.com/super-sim/) using the **Event Streams**, [**FastAPI**](https://fastapi.tiangolo.com/), and [**Leaflet**](https://leafletjs.com/) using [**OpenAI Codex**](https://openai.com/codex/)

You can download the code from my [**GitHub repository here**](https://github.com/naturalfunction/KORE-SUPERSIM-heatmap)

New to Event Streams? Start with my [**Getting Started with KORE SUPER SIM Event Streams**](/p/getting-started-with-kore-super-sim-event-streams/) guide first.

---

## ⭐ What the App Does
Super SIM Heatmap provides:

- Real-time Super SIM event ingestion  
- Persistent storage of CloudEvents payloads  
- Dual online/offline heatmap layers  
- Timeline slider for replay  
- Device event feed with metadata  
- Click-to-pan tower visualization  

---

## 🌍 Why Visualize Super SIM Events?
KORE SUPER SIM emits session lifecycle events such as:

- `connection.data-session.started`
- `connection.data-session.updated`
- `connection.data-session.ended`

Visualizing them helps teams understand connectivity patterns and issues across geography and time.

---

## 🧱 Architecture Overview
```
FastAPI     → Webhook ingestion  
SQLite      → Raw event persistence  
SQLModel    → ORM  
Leaflet     → Heatmap rendering  
Jinja2      → Templates  
```

---

## ⚡ Webhook Ingestion
The webhook endpoint:

```
POST /webhooks/supersim
```

Validates, extracts, and persists raw event payloads.

---

## 🔥 Dual-Layer Heatmap
- Green = online  
- Red = offline  

State is inferred by latest event per ICCID.

---

## ⏱ Timeline Scrubbing
Scrub 00:00–23:59 and reconstruct fleet activity by timestamp.

---

## 📋 Device Event Sidebar
Shows:

- ICCID  
- Tower  
- Network  
- RAT  
- Timestamp  

---

## 🤖 Synthetic Data Seeder
Simulates START → UPDATE → END events across global cities.

Example:

```
.venv/bin/python scripts/seed_events.py --region naples --devices 50 --count 550
```

---

## 🧪 Manual cURL Tests
Includes samples for all session lifecycle events.

---

## 🖥 Web UI Overview
- Device sidebar  
- Heatmap toggles  
- Timeline slider  
- Stats counters  

---

## 📁 Project Structure
```
app/
scripts/
templates/
static/
docs/
```

---

## 🛠 Quick Start
```
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```

---

![Terminal showing FastAPI server running with uvicorn reload command](run-project.png)

## 🛠 Seed sample data


50 devices in Naples, ~550 sessions total

```
.venv/bin/python scripts/seed_events.py --region naples --devices 50 --count 550
```

30 devices in every region, 5 sessions each
```
for region in naples toronto saopaulo lisbon shanghai capetown sydney; do
  .venv/bin/python scripts/seed_events.py --region "$region" --devices 30 --sessions-per-device 5
done
```

---

## 🛠 Map Examples

Map after seeding data
![Interactive heatmap showing SUPER SIM device locations with online and offline status indicators](heatmap.png)

Map after filtering data using the Timeline
![Heatmap filtered by timeline showing device activity at specific time period](heatmap-filtering-timeline.png)

Map after filtering data using the Timeline Online Only.
![Heatmap displaying only online devices filtered by timeline with green indicators](heatmap-filtering-timeline-online.png)

Map after filtering data using the Timeline Offline Only.
![Heatmap showing only offline devices filtered by timeline with red indicators](heatmap-filtering-timeline-offline.png)

Map after clicking SHOW ALL
![Zoomed heatmap view showing all device locations and connection towers at maximum zoom level](heatmap-filtering-timeline-showall-max-zoom.png)
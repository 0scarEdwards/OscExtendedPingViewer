# 🖥️ OscExtendedPingViewer  
**Developed by Oscar E**  

_A lightweight and intuitive Python desktop application for live network latency monitoring — complete with real-time graphs, color-coded health indicators, Excel exports, and optional email alerts for outages or high latency._

---

## 🧭 Overview  

**OscExtendedPingViewer** helps you monitor network latency in real time by pinging both a user-defined target (like a server or router) and a reliable external benchmark (Google's 8.8.8.8).  

- Results are displayed on a **live graph**.  
- A simple, **color-coded status indicator** shows current connection health.  
- Supports **optional email alerts** for:  
  - High latency  
  - Consecutive ping failures  
  - Extended outages  
- Sessions can be **exported to Excel (.xlsx)** for logging or analysis.  

---

## ✨ Features  

### • 📊 Live Dual Ping Graph  
Real-time matplotlib graph showing both your target and Google's 8.8.8.8 latency side-by-side.

### • 📁 Excel Export  
Save ping session data to a `.xlsx` file using pandas for easy review.

### • 🪄 Fully GUI Driven  
Built with `tkinter` — no terminal required.

---

## 🚦 Health Indicator  

| Color   | Meaning                              |
|---------|--------------------------------------|
| 🟢 Green  | Latency ≤ 50ms                       |
| 🟠 Amber  | Latency between 51–100ms             |
| 🔴 Red    | Latency > 100ms or ping failure      |
| ⚫ Grey   | No data yet (initial state)          |

---

## 🖼️ GUI Overview  

- **Target IP/Hostname**: Destination to ping (e.g., server, gateway, website).  
- **Interval (seconds)**: Time between pings (default: 30s, adjustable).  
- **Enable Email Alerts**: Toggle alerting system.  
- **Email Config Fields**:  
  - SMTP server and port  
  - Sender and recipient email addresses  
  - Login credentials  
- **Buttons**:  
  - `Start Monitoring`: Begins ping loop in background thread.  
  - `Stop Monitoring`: Gracefully stops the process.  

---

## 📤 Data Export  

Each export includes:  
- Timestamp  
- Latency to your target  
- Latency to 8.8.8.8 (Google DNS)  
- Health status (Green/Amber/Red)  

Exported as a `.xlsx` file using `pandas`.

---

## 🔔 Email Alerting Logic  

To prevent excessive notifications, alerts are sent **once per alert event**.

### Three types of alerts:  
- **Latency Warning**: Triggered when ping exceeds threshold.  
- **Consecutive Failures**: After multiple unreachable results.  
- **Extended Outage**: If target remains unreachable for over 2 minutes.

> 💡 **Email fields only need configuration if alerts are enabled.**

---

## 🔧 Installation  

Install the required Python libraries:  

```bash
pip install matplotlib pandas

#🖥️OscExtendedPingViewer
Developed by Oscar E
A lightweight and intuitive Python desktop application for live network latency monitoring — complete with real-time graphs, color-coded health indicators, Excel exports, and optional email alerts for outages or high latency.
________________________________________
🧭 Overview
OscExtendedPingViewer helps you monitor network latency in real time by pinging both a user-defined target (like a server or router) and a reliable external benchmark (Google's 8.8.8.8). Results are displayed on a live graph, while a simple, color-coded indicator shows the current connection status at a glance.
For added peace of mind, the app supports optional email alerts for high latency, consecutive ping failures, or extended outages. Sessions can be exported to Excel for logging or analysis.
________________________________________
✨ Features
•	📊 Live Dual Ping Graph
Real-time matplotlib graph showing both your target and 8.8.8.8 latency side-by-side.
•	📁 Excel Export
Save your ping session to a .xlsx file using pandas for easy review and record-keeping.
•	🪄 Fully GUI Driven
Built with tkinter—no terminal or command line required.
________________________________________
🚦 Health Indicator
A simple status dot provides visual feedback:
Color	Meaning
🟢 Green	Latency ≤ 50ms
🟠 Amber	Latency between 51–100ms
🔴 Red	Latency > 100ms or ping failure
⚫ Grey	No data yet (initial state)
________________________________________
🖼️ GUI Overview
•	Target IP/Hostname
The destination to ping (e.g., server, gateway, website).
•	Interval (seconds)
Time between pings (default: 30 seconds; adjustable).
•	Enable Email Alerts
Toggle email alerting on or off.
•	Email Config Fields
SMTP server, port, sender and recipient emails, login credentials.
•	Buttons
o	Start Monitoring — Launches the ping loop in a background thread.
o	Stop Monitoring — Gracefully stops the monitoring process.
________________________________________
📤 Data Export
Each export includes:
•	Timestamp
•	Latency to your target
•	Latency to 8.8.8.8 (internet benchmark)
•	Health status (Green/Amber/Red)
Saved as a .xlsx file using pandas.
________________________________________
🔔 Email Alerting Logic
To avoid alert fatigue, emails are only sent once per alert event.
Three alert types are monitored:
•	Latency Warning — Triggered when ping exceeds threshold.
•	Consecutive Failures — Triggered after multiple unreachable results.
•	Extended Outage — Triggered if the target remains unreachable for over 2 minutes.
💡 Email settings only need to be configured if alerts are enabled.
________________________________________
🔧 Installation
Install the required libraries (auto-handled if packaged):
bash
CopyEdit
pip install matplotlib pandas
________________________________________
🛠 Development Notes
•	Default ping interval is 30 seconds but can be adjusted in the UI.
•	GUI is built entirely with tkinter and ttk for a native look and feel.
________________________________________
📧 Email Setup Example
Field	Example
SMTP Server	smtp.gmail.com
SMTP Port	587
Sender Email	you@gmail.com
Recipient Email	alerts@yourdomain.com
SMTP Username	you@gmail.com
SMTP Password	your_app_password
🔐 Note: Gmail may require using App Passwords or enabling access for “Less Secure Apps”.
________________________________________
📃 License
MIT License — free to use, modify, and share. Credit is appreciated!
-Occie 😊

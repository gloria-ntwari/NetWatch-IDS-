# NetWatch IDS – Network Intrusion Detection System

NetWatch IDS is a lightweight Python-based Network Intrusion Detection System designed to monitor network traffic, identify potentially suspicious activities, and generate security alerts.

The project focuses on detecting unusual TCP connection patterns, particularly potential port scanning activities, and storing detected incidents for further analysis.

## Features

- **Network Traffic Monitoring:** Captures and analyzes TCP packets using Scapy.
- **Port Scan Detection:** Identifies potential port scanning based on repeated connection attempts to different destination ports.
- **Security Alerts:** Generates alerts containing the source IP, alert type, severity, and description.
- **Incident Storage:** Stores detected security incidents in an SQLite database.
- **Rule-Based Detection:** Uses configurable thresholds and time windows to identify suspicious network behavior.

## Technologies Used

- Python
- Scapy
- SQLite
- Git and GitHub

## Project Structure

```text
NetWatch-IDS/
│
├── backend/
│   ├── main.py
│   ├── detector.py
│   ├── packet_capture.py
│   └── database.py
│
├── requirements.txt
├── .gitignore
└── README.md
```

## How It Works

NetWatch IDS follows a simple detection workflow:

1. Captures TCP network packets.
2. Extracts source IP addresses and destination ports.
3. Analyzes connection patterns within a defined time window.
4. Identifies potential port scanning behavior.
5. Generates security alerts when detection thresholds are reached.
6. Stores incidents in an SQLite database.

## Installation

### Prerequisites

- Python 3.10 or later
- Npcap on Windows for live packet capture
- Administrator privileges may be required for packet capture.

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/netwatch-ids.git
cd netwatch-ids
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it on Windows:

```powershell
.\venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

## Running the Application

Start the packet monitoring engine:

```bash
python backend/packet_capture.py
```

To stop monitoring, press `CTRL + C`.

## Detection Methodology

The current detection engine uses rule-based analysis.

For example, it flags a potential TCP port scan when a single source IP attempts to contact at least 10 different destination ports within a 10-second window.

The detection threshold and time window can be adjusted to suit different testing environments.

## Testing

The detection logic can be tested using simulated connection attempts before enabling live packet capture.

Testing should be conducted in an authorized environment using systems and networks you own or have permission to assess.

## Future Improvements

- Additional detection rules for suspicious traffic patterns.
- Improved alert classification and prioritization.
- Network interface selection.
- Enhanced incident analysis and reporting.
- Web-based security monitoring dashboard.

## Security and Ethical Use

NetWatch IDS is intended for educational purposes, cybersecurity research, and authorized network monitoring.

Only monitor networks and systems for which you have explicit permission.

## Author

**Gloria Irasubiza**

GitHub: https://github.com/YOUR_USERNAME
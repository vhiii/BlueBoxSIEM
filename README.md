# BlueBoxSIEM
A Windows File server with a custom built SIEM for real time event monitoring and security analysis. Developed as part of a hands on cybersecurity project and homelab. 

# Overview
**BlueBoxSIEM** is a full stack cybersecurity project that transforms a standard Windows 22 File Server into a security hardened, event monitored environment. This solution collects, parses, and analyzes logs in real-time to detect suspicious behavior such as unauthorized file access, brute force login attempts, and privilege misuse.

# Features
- Secure Windows File Server with custom permissions
- Auditing and logging of key events (e.g., 4624, 4663, 4625)
- PowerShell log exporter and automation
- Python-based log parser and alert engine
- Simulated attack scripts to test SIEM effectiveness
- Visual dashboards for event trend analysis

# Architecture Diagram
<table>
<tr>
<td>

<img src="https://github.com/user-attachments/assets/d721af41-cffb-4931-bdc5-c9293154bbdf" width="300"/>

</td>
<td>

<pre>
            +-------------------+
            |   File Server     |
            |  (Windows 2022)   |
            +--------+----------+
                     |
                     | Log Events (Event Viewer)
                     v
        +------------+------------+
        | PowerShell Export Script|
        +------------+------------+
                     |
                     | JSON/CSV Log Output
                     v
        +------------+------------+
        |   Python SIEM Parser    |
        |  - Rule Engine          |
        |  - Alert Dispatcher     |
        +------------+------------+
                     |
                     | Alerts (CLI, Email, Log)
                     v
               [Alert Output Layer]

</pre>

</td>
</tr>
</table>

# Project Structure
<table>
<tr>
<td>

<img src="https://github.com/user-attachments/assets/885788cf-2eef-4bc7-99f2-37b6d2e08ff9" width="300"/>

</td>
<td>

<pre>
BlueBoxSIEM/
├── README.md                 # Project overview and usage
├── docs/                    # Diagrams and event references
│   ├── architecture.png
│   └── event-IDs.md
├── powershell/              # Windows event log export scripts
│   ├── export-logs.ps1
│   └── scheduled-task.xml
├── siem/                    # Python-based SIEM logic
│   ├── parser.py
│   ├── rules.json
│   └── alert_engine.py
├── test-scripts/            # Simulated attacks to trigger logs
│   └── simulate_failed_logins.ps1
├── logs/                    # Sample exported logs
└── .gitignore               # Ignore unnecessary files in Git
</pre>

</td>
</tr>
</table>

# Usage
1. Clone the repo and deploy the Windows File Server.
2. Configure file shares and permissions.
3. Enable auditing via Group Policy or local security settings.
4. Use the Powershell script to export logs periodically.
5. Run the Siem engine to parse and analyze logs.
6. Review alerts and log outputs.

# Event IDs Monitored
- 4624: Successful Logon
- 4625: Failed Logon
- 4663: File Access Attempted
- 4670: Permissions Change
- 4720: User Account Created

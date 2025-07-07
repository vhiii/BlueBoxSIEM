# BlueBoxSIEM Build Process Documentation

This document outlines the progress, configuration, and rationale behind building the BlueBoxSIEM Windows file server with custom logging and auditing.

---

Part 1: Windows Server Setup
- Created a new Windows Server 2022 VM on Azure
- Installed File Server role via Server Manager
- Created C:\SharedFiles and configured NTFS permissions
- Created local user 'testuser'
- Enabled SMB sharing on the folder

![folder-audit-settings](https://github.com/user-attachments/assets/a8ec6632-f9bc-46da-a9e8-ead964c07fb1)
![gp-audit-object-access](https://github.com/user-attachments/assets/206f2a62-8d08-46e3-b3f0-f19aeae93f29)
![eventviewer-audit-filtered](https://github.com/user-attachments/assets/074dffd3-2b68-47ee-af48-e6700f66fe9f)
![event-4663-example](https://github.com/user-attachments/assets/7922de1c-5b61-4879-9f6e-8ae412e9336e)
![powershell-log-export](https://github.com/user-attachments/assets/dac310df-e714-47a8-8411-cf165ad2b019)

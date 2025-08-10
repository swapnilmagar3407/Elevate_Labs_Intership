# GVM (Greenbone Vulnerability Manager) on Kali Linux

## Overview
This guide explains how to install, configure, and run GVM (Greenbone Vulnerability Manager) on Kali Linux, including fixing the "default Scan Config not available" error.

---

## Installation

```bash
sudo apt update && sudo apt install gvm -y
```

Initialize GVM:
```bash
sudo gvm-setup
```

Check service status:
```bash
sudo gvm-check-setup
```

---

## Feed Synchronization

GVM uses multiple data feeds:
- **NVT (Network Vulnerability Tests)**
- **SCAP (Security Content Automation Protocol)**
- **CERT (Computer Emergency Response Team advisories)**
- **GVMD_DATA** (scan configs, port lists, policies)

Run feed updates manually:
```bash
sudo runuser -u _gvm -- greenbone-nvt-sync
sudo runuser -u _gvm -- greenbone-feed-sync --type SCAP
sudo runuser -u _gvm -- greenbone-feed-sync --type CERT
sudo runuser -u _gvm -- greenbone-feed-sync --type GVMD_DATA
```

Check status in the web UI: **Configuration → Feed Status**  
Wait until all say **Current** instead of `Update in progress...`.

---

## Running a Scan

1. Login to GVM Web UI:
   ```
   https://127.0.0.1:9392
   ```
2. Create a **Target** (IP or hostname).
3. Create a **Task** and select a **Scan Config**.
4. Start the scan and view results.

---

## Troubleshooting

### Error: `default Scan Config is not available`
- This happens if feeds haven’t finished syncing.
- Wait until **SCAP**, **CERT**, and **GVMD_DATA** show `Current`.
- Then restart GVM:
```bash
sudo gvm-stop
sudo gvm-start
```

###  Feed Sync Takes Too Long
- First sync can take **15 min – 3+ hours** depending on your network speed.
- Monitor logs in real-time:
```bash
tail -f /var/log/gvm/gvmd.log
tail -f /var/log/gvm/gsad.log
tail -f /var/log/gvm/openvas.log
```

---

##  License
MIT License

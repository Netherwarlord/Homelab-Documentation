
This repository contains the documentation for my personal homelab environment. This setup serves as a practical learning tool for systems administration, networking, and containerization, running 24/7.

</div>

---

### 📊 Live Homelab Status

> These panels are rendered live from my Grafana instance (via an Nginx reverse proxy), providing real-time insight into my server's operations.

<div align="center">
  <img src="https://grafana.infernalaquatics.com/d-solo/rYdddlPWk/node-exporter-full?orgId=1&panelId=20&render=1&theme=dark" alt="CPU Busy Gauge" width="450" height="200" frameborder="0"/>
  <img src="https://grafana.infernalaquatics.com/d-solo/rYdddlPWk/node-exporter-full?orgId=1&panelId=155&render=1&theme=dark" alt="System Load Gauge" width="450" height="200" frameborder="0"/>
  <img src="https://grafana.infernalaquatics.com/d-solo/rYdddlPWk/node-exporter-full?orgId=1&panelId=16&render=1&theme=dark" alt="RAM Usage Gauge" width="450" height="200" frameborder="0"/>
  <br/>
  <img src="https://grafana.infernalaquatics.com/d-solo/rYdddlPWk/node-exporter-full?orgId=1&panelId=77&render=1&theme=dark" alt="CPU Usage Chart" width="45%" height="250" frameborder="0"/>
  <img src="https://grafana.infernalaquatics.com/d-solo/rYdddlPWk/node-exporter-full?orgId=1&panelId=78&render=1&theme=dark" alt="Memory Usage Chart" width="45%" height="250" frameborder="0"/>
  <br/>
  <img src="https://grafana.infernalaquatics.com/d-solo/rYdddlPWk/node-exporter-full?orgId=1&panelId=74&render=1&theme=dark" alt="Network Traffic Chart" width="100%" height="250" frameborder="0"/>
</div>

---

### 🛠️ Hardware Infrastructure

| Component         | Model/Details                                       | Role                                           |
| ----------------- | --------------------------------------------------- | ---------------------------------------------- |
| **Primary Server** | HPE ProLiant DL380P Gen8                            | Main host for all containerized services.      |
| **CPU** | 2x Intel Xeon E5-2650 @ 2.00GHz (16 Cores / 32 Threads) | Powers all virtual machines and containers.    |
| **RAM** | 64GB ECC RAM                                        | Provides memory for all running applications.  |
| **Network Switch** | Netgear GS108tv3 Managed Switch                     | Manages network traffic and VLANs for the lab. |
| **Power Workstation** | Alienware M15 (i7-9750H, 32GB, RTX 2060)            | Primary Windows client and testing machine.    |

---

### 📦 Software & Services

My entire software stack is managed via Docker and Docker Compose for easy deployment, scaling, and maintenance.

* **Host OS:** **Ubuntu Server** on the HPE ProLiant.
* **Containerization:** **Docker & Docker Compose**.
* **Key Services:**
    * **Odoo:** Used for helpdesk ticketing and project management (migrated from Nextcloud).
    * **RustDesk:** Self-hosted server for secure remote access to lab machines.
    * **Samba:** Provides a centralized NAS file share, mounted as a network drive on Windows clients for high-performance storage (e.g., Steam library).
    * **Grafana & Prometheus:** Powers the live status monitoring panel.

---

### 🌐 Network Diagram

*(This is optional but highly recommended. You can use a free tool like `diagrams.net`, create a simple diagram, save it as a PNG, upload it to this repository, and then link to it here.)*

`![Network Diagram](network-diagram.png)`

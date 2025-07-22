<div align="center">

# Christopher's Homelab Documentation

This repository contains the documentation for my personal homelab environment. This setup serves as a practical learning tool for systems administration, networking, and containerization, running 24/7.

</div>

---

### 📊 Live Homelab Status

> To provide live insight into my server's operations, I use Uptime Kuma, a self-hosted monitoring tool running in a Docker container. It provides real-time status for my key services.

<p align="center">
  <!-- These are placeholder badges. Once Uptime Kuma is set up, you will replace these with your actual status page links. -->
  <img src="https://img.shields.io/badge/Server%20Status-Online-brightgreen?style=for-the-badge&logo=serverless" alt="Server Status"/>
  <img src="https://img.shields.io/badge/Network-Operational-blue?style=for-the-badge&logo=ubiquiti" alt="Network Status"/>
  <img src="https://img.shields.io/badge/Services-Stable-blueviolet?style=for-the-badge&logo=docker" alt="Services Status"/>
</p>

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
    * **Uptime Kuma:** Powers the live status monitoring panel.

---

### 🌐 Network Diagram

*(This is optional but highly recommended. You can use a free tool like `diagrams.net`, create a simple diagram, save it as a PNG, upload it to this repository, and then link to it here.)*

`![Network Diagram](network-diagram.png)`

---

### 🚀 Setting Up Live Monitoring

To implement the live status badges, I recommend deploying Uptime Kuma via Docker. Here is a sample `docker-compose.yml` snippet to get started:

```yaml
version: '3.3'
services:
  uptime-kuma:
    image: louislam/uptime-kuma:1
    container_name: uptime-kuma
    volumes:
      - ./uptime-kuma-data:/app/data
    ports:
      - "3001:3001"  # Port for the web UI
    restart: always

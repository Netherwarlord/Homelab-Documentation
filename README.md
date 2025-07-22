# My Homelab Documentation

This repository contains the documentation for my personal homelab environment. This setup serves as a practical learning tool for systems administration, networking, and containerization, running 24/7.

## Hardware Infrastructure

| Component            | Model/Details                               | Role                                           |
| -------------------- | ------------------------------------------- | ---------------------------------------------- |
| **Primary Server** | HPE ProLiant DL380P Gen8                    | Main host for all containerized services.      |
| **Network Switch** | Netgear GS108tv3 Managed Switch             | Manages network traffic and VLANs for the lab. |
| **Power Workstation**| Alienware M15 (i7-9750H, 32GB, RTX 2060)    | Primary Windows client and testing machine.    |

## Software & Services

* **Operating System:** Ubuntu Server on the HPE ProLiant.
* **Containerization:** Docker & Docker Compose for service management.
* **Key Services:**
    * **Odoo:** Used for helpdesk ticketing and project management (migrated from Nextcloud).
    * **RustDesk:** Self-hosted server for secure remote access to lab machines.
    * **Samba:** Provides a centralized NAS file share, mounted as a network drive on Windows clients for high-performance storage (e.g., Steam library).

## Network Diagram

*(This is optional but highly recommended. You can use a free tool like `diagrams.net`, create a simple diagram, save it as a PNG, upload it to this repository, and then link to it here.)*

`![Network Diagram](network-diagram.png)`

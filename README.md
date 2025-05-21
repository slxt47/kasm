# 🖥️ Kasm Workspaces – Standalone Docker Installation

This repository provides a simple setup for running **Kasm Workspaces** on a standalone server using Docker and Docker Compose.

> 💡 Kasm Workspaces is a container streaming platform that delivers secure, web-based access to desktops, applications, and command-line tools.

---

## 🌐 Live Preview

Once running, access your workspace at:

https:/<Server-IP>:443


---

## ⚙️ Requirements

- Linux server (Ubuntu 20.04/22.04 recommended)
- `docker` and `docker-compose` installed
- At least **8 GB RAM** and **2 CPU cores** recommended

### Install Docker

```bash
sudo apt update
sudo apt install -y docker.io docker-compose
sudo systemctl enable --now docker
````

### docker-compose.yml

version: '3'

services:
  kasm:
    image: kasmweb/core:1.14.0
    container_name: kasm
    ports:
      - "443:443"
    volumes:
      - kasm_data:/opt
    restart: unless-stopped

volumes:
  kasm_data:


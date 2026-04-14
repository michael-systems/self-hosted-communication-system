# Self-Hosted Communication System

A self-hosted communication system with private messaging, file exchange, and real-time audio/video calls.

This repository documents a real system built to provide infrastructure-controlled communication without relying on public messaging platforms.

---

## What it does

- provides private messaging through a self-hosted setup
- supports real-time audio and video calls
- enables file exchange between users
- allows domain-based external access across home, mobile, and remote networks
- maintains observable system state through monitoring

---

## Why it was built

Public messaging platforms were not a reliable foundation for daily communication in a restricted network environment.

The goal was to create a system that:
- remains accessible through a personal domain
- works across Wi-Fi and mobile networks
- does not depend entirely on third-party services
- provides direct control over infrastructure and data flow

---

## Architecture

The system is built around a self-hosted Raspberry Pi 5 node (Alfred) and includes:

- **Caddy** — reverse proxy and HTTPS entry point
- **Nextcloud + Talk** — messaging, calls, and file exchange
- **MariaDB** — backend database
- **coturn** — TURN relay for WebRTC calls
- **Uptime Kuma** — monitoring

High-level flow:

Users → Internet → Domain → Router → Alfred → Communication services

Real-time calls are supported through a TURN relay to ensure stable connectivity across Wi-Fi and mobile networks.

---

## Core functionality

- self-hosted messaging system
- real-time audio/video calls with TURN relay support
- file exchange between users
- domain-based external access
- monitoring of service availability

---

## Technical stack

### Infrastructure
- Raspberry Pi 5
- Debian 12
- Docker / Docker Compose

### Networking / Access
- Caddy reverse proxy
- domain + DNS
- port forwarding (ASUS router)

### Application layer
- Nextcloud + Talk
- MariaDB

### Real-time communication
- coturn (TURN server)

### Monitoring
- Uptime Kuma

---

## Complexity

This project required more than a basic application setup.

The main complexity was ensuring stable real-time communication across different network conditions. WebRTC calls required a properly configured TURN relay to function reliably beyond a local network, including mobile (4G) scenarios.

Additional complexity came from:
- reverse proxy configuration
- domain-based access
- NAT traversal
- full self-hosted deployment on local hardware

---

## Outcome

The system is live and used in practice by multiple users for messaging, calls, and conference scenarios.

It provides:
- working communication across home and external networks
- reliable real-time calls supported by TURN relay
- file exchange through a self-hosted platform
- observable service state through monitoring

---

## Proof

This repository includes:

- architecture diagrams
- screenshots of active calls
- TURN relay configuration proof
- monitoring dashboard
- case summary PDF

---

## Repository structure

```text
docs/
screenshots/
README.md
```
## Important note

This is a technical case repository, not a production deployment repository.

Sensitive configuration details, credentials, and internal infrastructure data are intentionally excluded.

Author

Built as an independent project focused on self-hosted communication, real-time systems, and infrastructure design.

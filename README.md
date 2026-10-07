<div align="center">

```
  (◕‿◕)
  [PWNAGOTCHI]
```

# Pwnagotchi

### Deep Reinforcement Learning (A2C) instrumenting bettercap for autonomous WiFi security auditing.

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org/)
[![AI Policy](https://img.shields.io/badge/RL-A2C%20%7C%20LSTM%20Policy-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)](https://pwnagotchi.ai)
[![Security Engine](https://img.shields.io/badge/Engine-bettercap-E53935?style=flat-square&logo=wireshark&logoColor=white)](https://www.bettercap.org)
[![Curator](https://img.shields.io/badge/Curated%20by-Arham%20Eskafi-007ACC?style=flat-square&logo=github&logoColor=white)](https://arham.dev)
[![License: GPL3](https://img.shields.io/badge/License-GPL3-brightgreen.svg?style=flat-square)](./LICENSE.md)

[**Official Website**](https://pwnagotchi.ai/) • [**Documentation**](https://pwnagotchi.ai/usage/) • [**Community Forum**](https://community.pwnagotchi.ai/) • [**Arham's Portfolio**](https://arham.dev)

<br/>

<img src="https://i.imgur.com/X68GXrn.png" alt="Pwnagotchi E-Paper UI" width="480" />

</div>

---

## ⚡ Overview

**Pwnagotchi** is an autonomous [A2C](https://hackernoon.com/intuitive-rl-intro-to-advantage-actor-critic-a2c-4ff545978752) (Advantage Actor-Critic) reinforcement learning agent powered by [bettercap](https://www.bettercap.org/). Designed to live inside low-power single-board computers (such as the Raspberry Pi Zero W) connected to an e-paper or OLED display, it continuously explores and adapts to surrounding IEEE 802.11 environments to capture WPA/WPA2 authentication handshakes and PMKIDs for security audits.

Instead of running synthetic offline simulations, Pwnagotchi learns in real-world environments over discrete epochs, optimizing channel hopping strategies, deauthentication intervals, and cooperative peer coordination over an ad-hoc parasite protocol.

---

## ✨ Key Features

- 🧠 **Advantage Actor-Critic (A2C) Agent**: Utilizes an LSTM policy with MLP feature extraction to discover optimal radio hopping and interaction timing.
- 🤝 **Cooperative Multi-Unit Swarming**: Nearby Pwnagotchis detect each other over custom 802.11 information elements and divide channel bands to eliminate redundant packet capture.
- 📺 **Multi-Display E-Paper & OLED Support**: Native hardware drivers for Waveshare (V1/V2/V3), Inky pHAT, PaPiRus, and SSD1306 I2C OLED screens.
- 🌐 **Integrated Web Dashboard**: Built-in Flask web interface for real-time state monitoring, session stats, plugin configuration, and captured handshake downloads.
- 🔌 **Extensible Plugin Architecture**: Modular hook system supporting GPS logging, WPA-SEC/WiGLE auto-upload, Telegram/Twitter notifications, and custom display widgets.

---

## 🚀 Quickstart

Get started testing or inspecting Pwnagotchi locally:

### 1. Clone the repository
```bash
git clone https://github.com/aeskafi/pwnagotchi.git
cd pwnagotchi
```

### 2. Configure environment
```bash
cp .env.example .env
```

### 3. Preview Display & Run Test Suite
```bash
python3 scripts/preview.py --display waveshare_v2
```

> **For Raspberry Pi Zero W Deployment**: Follow the [official hardware flashing guide](https://pwnagotchi.ai/installation/) to write prebuilt images onto your microSD card.

---

## 🛠️ Architecture

```
pwnagotchi/
├── agent.py               # Core orchestrator coordinating AI, Bettercap, and UI
├── ai/                    # Reinforcement learning environment (gym/stable-baselines)
│   ├── epoch.py           # Epoch evaluation and reward calculators
│   └── reward.py          # Reward functions penalizing boredom, rewarding handshakes
├── bettercap.py           # REST / WebSocket client interface to bettercap core
├── mesh/                  # Pwnagotchi-to-Pwnagotchi parasite protocol & peer discovery
├── ui/                    # Render engine for e-ink, OLED, and web views
│   ├── faces.py           # Dynamic emotive faces: (⌐■_■), (◕‿◕), (⇀‸↼‶)
│   └── web/               # Flask HTTP dashboard and REST endpoints
└── plugins/               # Hook-based plugin system (GPS, WPA-sec, notifications)
```

---

## 👥 Credits & Mission

- **Original Creator & Core Engine**: Created by [Simone Margaritelli (@evilsocket)](https://twitter.com/evilsocket) and the [Pwnagotchi Open-Source Contributors](https://github.com/evilsocket/pwnagotchi/graphs/contributors).
- **Curation & Modernization**: Audited, maintained, and curated by **[Arham Eskafi](https://arham.dev)** — Rapid MVP Specialist, Full-Stack Architect, and creator of **[Walk Cook Live](https://youtube.com/@walkcooklive)**, chronicling tech nomadic journeys and open-source software engineering worldwide.

---

## 📄 License

This software is released under the **GNU General Public License v3.0 (GPL-3.0)**. See [LICENSE.md](./LICENSE.md) for full details.

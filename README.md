<!-- BlackRoad SEO Enhanced -->

# ulackroad warehouse optimizer

> Part of **[BlackRoad OS](https://blackroad.io)** — Sovereign Computing for Everyone

[![BlackRoad OS](https://img.shields.io/badge/BlackRoad-OS-ff1d6c?style=for-the-badge)](https://blackroad.io)
[![BlackRoad OS](https://img.shields.io/badge/Org-BlackRoad-OS-2979ff?style=for-the-badge)](https://github.com/BlackRoad-OS)
[![License](https://img.shields.io/badge/License-Proprietary-f5a623?style=for-the-badge)](LICENSE)

**ulackroad warehouse optimizer** is part of the **BlackRoad OS** ecosystem — a sovereign, distributed operating system built on edge computing, local AI, and mesh networking by **BlackRoad OS, Inc.**

## About BlackRoad OS

BlackRoad OS is a sovereign computing platform that runs AI locally on your own hardware. No cloud dependencies. No API keys. No surveillance. Built by [BlackRoad OS, Inc.](https://github.com/BlackRoad-OS-Inc), a Delaware C-Corp founded in 2025.

### Key Features
- **Local AI** — Run LLMs on Raspberry Pi, Hailo-8, and commodity hardware
- **Mesh Networking** — WireGuard VPN, NATS pub/sub, peer-to-peer communication
- **Edge Computing** — 52 TOPS of AI acceleration across a Pi fleet
- **Self-Hosted Everything** — Git, DNS, storage, CI/CD, chat — all sovereign
- **Zero Cloud Dependencies** — Your data stays on your hardware

### The BlackRoad Ecosystem
| Organization | Focus |
|---|---|
| [BlackRoad OS](https://github.com/BlackRoad-OS) | Core platform and applications |
| [BlackRoad OS, Inc.](https://github.com/BlackRoad-OS-Inc) | Corporate and enterprise |
| [BlackRoad AI](https://github.com/BlackRoad-AI) | Artificial intelligence and ML |
| [BlackRoad Hardware](https://github.com/BlackRoad-Hardware) | Edge hardware and IoT |
| [BlackRoad Security](https://github.com/BlackRoad-Security) | Cybersecurity and auditing |
| [BlackRoad Quantum](https://github.com/BlackRoad-Quantum) | Quantum computing research |
| [BlackRoad Agents](https://github.com/BlackRoad-Agents) | Autonomous AI agents |
| [BlackRoad Network](https://github.com/BlackRoad-Network) | Mesh and distributed networking |
| [BlackRoad Education](https://github.com/BlackRoad-Education) | Learning and tutoring platforms |
| [BlackRoad Labs](https://github.com/BlackRoad-Labs) | Research and experiments |
| [BlackRoad Cloud](https://github.com/BlackRoad-Cloud) | Self-hosted cloud infrastructure |
| [BlackRoad Forge](https://github.com/BlackRoad-Forge) | Developer tools and utilities |

### Links
- **Website**: [blackroad.io](https://blackroad.io)
- **Documentation**: [docs.blackroad.io](https://docs.blackroad.io)
- **Chat**: [chat.blackroad.io](https://chat.blackroad.io)
- **Search**: [search.blackroad.io](https://search.blackroad.io)

---


> Warehouse layout optimization with ABC velocity analysis, slot scoring, and placement recommendations.

## Features

- **ABC analysis** — Pareto 80/15/5 velocity classification
- **Slot scoring engine** — considers aisle proximity, level, product weight, volume fit, category match
- **Placement recommendations** ranked by score
- **Optimization report** — identifies misplaced items and generates MOVE / REPLENISH actions
- **Utilization heatmap** — ASCII visualization by aisle × row
- **Bulk slot creation** for rapid warehouse setup
- **Low-stock alerts** integrated into optimization

## Quick Start

```bash
pip install -e .

# Create warehouse layout
python src/warehouse_optimizer.py bulk-slots 10 20 --levels 4 --zone A

# Add products
python src/warehouse_optimizer.py add-product SKU-001 "FastWidget" electronics 2.5 --picks 200
python src/warehouse_optimizer.py add-product SKU-002 "SlowWidget" general 1.0 --picks 5

# Get placement recommendation
python src/warehouse_optimizer.py recommend SKU-001

# Place product
python src/warehouse_optimizer.py place SKU-001 s010101 --qty 50

# Run ABC classification
python src/warehouse_optimizer.py analyze

# Optimize layout
python src/warehouse_optimizer.py optimize

# Utilization report + heatmap
python src/warehouse_optimizer.py report
python src/warehouse_optimizer.py heatmap
```

## CLI Reference

| Command | Description |
|---------|-------------|
| `add-slot AISLE ROW LEVEL [--zone] [--type]` | Add single slot |
| `bulk-slots AISLES ROWS [--levels] [--zone]` | Bulk create |
| `add-product SKU NAME CAT WEIGHT [--picks]` | Add product |
| `place SKU SLOT_ID [--qty]` | Place product in slot |
| `recommend SKU [--top N]` | Suggest best slots |
| `analyze` | ABC velocity analysis |
| `optimize` | Layout recommendations |
| `report` | Utilization statistics |
| `heatmap` | ASCII utilization map |
| `list-products` | All products with velocity |

## Slot Scoring Formula

Score is influenced by:
1. **Aisle proximity** (A-items favour aisles 1–3, C-items prefer far aisles)
2. **Level suitability** (heavy items penalised above level 1)
3. **Volume fit** (ratio of product volume to slot volume)
4. **Category match** (refrigerated/hazmat slots match product category)

## Development

```bash
pytest tests/ -v --cov=src
```

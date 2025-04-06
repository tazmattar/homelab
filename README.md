# Pantry Network – Homelab Overview

Welcome to the **Pantry Network**, a purpose-built homelab designed for network experimentation, studio productivity, and service automation. This setup supports everything from Proxmox clustering to smart home integration and studio backup workflows.

---

## Key Goals
- Maintain a reliable, high-speed home network
- Host virtualized services (Proxmox Cluster)
- Ensure data redundancy with dual-linked NAS
- Segment traffic with VLANs for performance and security
- Monitor and manage power usage with UPS integration
- Serve studio needs (Mac Mini with Pro Tools)
- Document everything for reproducibility and learning

---

## Core Infrastructure

- **UDM Pro** as the primary router/firewall
- **UniFi Switches** (2.5G, PoE, SFP+) handle segmentation and performance
- **Proxmox Cluster** on 3 x Dell Optiplex 3040 MFF nodes
- **Proxmox Backup Server** for snapshotting and nightly backups
- **UNAS Pro** (10GbE + 1GbE) for studio archive storage
- **Synology NAS (Broadstairs)** for home backups
- **Mac Mini M4** for studio production and daily tasks
- **Pi-hole** for DNS ad-blocking and redundancy (VM + HA)
- **APC UPS** for power protection and monitoring

---

## Network Layout

📂 See [`network/pantry-network.md`](./pantry-network.md) for full documentation  
📜 View the [Mermaid Diagram](./topology.md) for a code-based network map  
🖼️ Or open the [Freeform PDF Topology](./topology.pdf) for a visual reference

---


## VLANs

| VLAN ID | Name             |
|---------|------------------|
| 1       | Core Network     |
| 2       | VoIP Network     |
| 20      | Homelab/Studio   |
| 30      | House            |
| 40      | IoT Devices      |
| 50      | Pentesting       |


## What's Next?

- [ ] Add automation playbooks (Ansible)
- [ ] Monitor services via Prometheus + Grafana
- [ ] Publish blog posts documenting each stage (see: [Pantry Network blog](pantrynetwork.io))

---

Stay tuned as I expand the network and explore new tools.

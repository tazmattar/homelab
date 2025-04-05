# Pantry Network – Home Lab Documentation

## 🧠 Network Overview
A robust home network segmented into House and Studio zones. Managed by a UDM Pro SE, supported by UniFi switches, running a Proxmox cluster, with dual-linked NAS and isolated VLANs.

---

## 🌐 Network Topology
- **Router**: UniFi Dream Machine Pro SE (10.28.28.1)
- **Main Switches**:
  - USW Flex 2.5G 5-Port (Core switch for Proxmox + Mac Mini)
  - UniFi Switch 16 PoE (Studio switching)
  - UniFi Switch Pro 8 PoE (House switching)

---

## 🖥️ Core Devices

| Device            | Role/Use                | Connection        | VLAN         | Notes                          |
|-------------------|--------------------------|--------------------|--------------|--------------------------------|
| Proxmox Node 1-3 | Cluster / VMs           | 2.5GbE (Flex)      | VLAN 30      | Dell Optiplex 3040 MFF         |
| Mac Mini M4       | Audio production         | 2.5GbE (Flex)      | VLAN 30      | Runs Pro Tools + backups       |
| UNAS Pro NAS      | Studio archive storage   | 10GbE + 1GbE       | VLAN 20      | Connected via SFP+ and 1GbE    |
| Synology NAS      | Home backup              | 1GbE (Switch Pro 8)| VLAN 30      | Labelled “Broadstairs”         |
| APC UPS           | Power backup + monitor   | USB/Network        | N/A          | Connected to Proxmox cluster   |

---

## 📡 Access Points

| AP Location     | Switch          | VLAN | Notes                    |
|------------------|------------------|-------|---------------------------|
| Bedroom AP       | Switch Pro 8 PoE | 30    | For wireless in house     |
| Living Room AP   | Switch Pro 8 PoE | 30    | For smart TV + IoT        |
| Studio AP        | Switch 16 PoE    | 30    | For studio devices        |
| TV IoT AP        | Switch 16 PoE    | 30    | Dedicated to smart TV     |

---


## 🔄 VLANs

| VLAN ID | Name             |
|---------|------------------|
| 1       | Core Network     |
| 2       | VoIP Network     |
| 20      | Homelab/Studio   |
| 30      | House            |
| 40      | IoT Devices      |
| 50      | Pentesting       |


## ⚡ Power & Monitoring

- **APC UPS** powers the Proxmox Cluster and is connected for monitoring.
- UDM Pro SE and switches are on battery-backed outlets.

---

## 🏠 Zones

**House:**
- Switch Pro 8 PoE
- Synology NAS
- Bedroom & Living Room APs
- IoT/TV Devices

**Studio:**
- Switch 16 PoE
- Studio AP, Printer, PC
- UNAS Pro NAS

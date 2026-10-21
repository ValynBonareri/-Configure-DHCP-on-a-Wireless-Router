# -Configure-DHCP-on-a-Wireless-Router
# Cisco Packet Tracer - DHCP Configuration on a Wireless Router

## Overview
This project demonstrates how to configure dynamic IP addressing (DHCP), basic wireless security, and LAN/WAN interface parameters on a home/SOHO wireless router using **Cisco Packet Tracer**. 

It simulates a standard Small Office/Home Office (SOHO) network setup where client devices (laptops, PCs, mobile devices) dynamically obtain network configuration details from a central wireless access gateway.

---

## Network Architecture & Design

### Topology
- **1x Home/Wireless Router** (DHCP Server & Gateway)
- **1x ISP / External Gateway** (WAN Connection)
- **Wired End Hosts** (Management PC / Desktop)
- **Wireless End Hosts** (Laptops / Smart Devices)

### Addressing Table

| Device | Interface | IP Address / Type | Subnet Mask | Default Gateway |
| :--- | :--- | :--- | :--- | :--- |
| **Wireless Router** | Internet (WAN) | DHCP / Static ISP IP | `255.255.255.0` | ISP Gateway IP |
| **Wireless Router** | Local Network (LAN)| `192.168.0.1` | `255.255.255.0` | N/A |
| **PC / Laptop Clients**| Wireless / Ethernet| **DHCP Dynamic Pool** | `255.255.255.0` | `192.168.0.1` |

---

## Key Configurations Implemented

### 1. Wireless Router GUI / Setup
* **LAN Configuration:**
  * Router IP Address: `192.168.0.1`
  * Subnet Mask: `255.255.255.0`
* **DHCP Pool Settings:**
  * Status: **Enabled**
  * Start IP Address: `192.168.0.100`
  * Maximum Number of Users: `50`
  * Static DNS (if applicable): `8.8.8.8` or local DNS server address

### 2. Wireless Security & SSID
* **Network Name (SSID):** `Home Network` (or custom SSID)
* **Wireless Security Type:** `WPA2-Personal` (AES)
* **Passphrase/Pre-Shared Key:** `[Your-Secure-Passphrase]`

---

## Verification & Testing

To confirm full network connectivity and functional DHCP assignment:

1. **Host DHCP Request Test:**
   * Set client NIC cards to **DHCP**.
   * Verify clients receive valid IP assignments within the `192.168.0.100`–`192.168.0.149` range, along with gateway (`192.168.0.1`) and DNS configuration.

2. **Command Line Connectivity Verification:**
   * Open the Command Prompt on a connected client device.
   * Run IP verification:
     ```cmd
     ipconfig /all
     ```
   * Renew DHCP lease:
     ```cmd
     ipconfig /renew
     ```
   * Test ICMP ping connectivity to the local gateway and remote host:
     ```cmd
     ping 192.168.0.1
     ```

---

## How to Run the Simulation

1. Download and install **Cisco Packet Tracer** (v8.0+ recommended).
2. Clone this repository:
   ```bash
   git clone [https://github.com/](https://github.com/)<Valyn_Bonareri>/packet-tracer-dhcp-wireless-router.git

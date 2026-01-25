# SIMULATION OF NETWORK DEVICES USING CISCO PACKET TRACER

## OBJECTIVE
The main objectives of this lab are:
1. To understand the working of basic network devices such as Hub, Switch, Bridge, Router, and Repeater.  
2. To design and simulate a small computer network using Cisco Packet Tracer.  
3. To assign IP addresses and verify communication between different devices.  
4. To analyze data flow within the same network and between different networks.  

---

## TOOLS USED
- Cisco Packet Tracer  
- Computer System  

---

## THEORY

### Cisco Packet Tracer
Cisco Packet Tracer is a network simulation and visualization tool developed by Cisco Systems. It is used to design, configure, and test computer networks in a virtual environment without using real hardware. It allows students to practice networking concepts such as IP addressing, routing, switching, and device configuration.

---

## COMPONENTS USED IN CISCO PACKET TRACER

### 1. End Devices
End devices are devices that generate or receive data.

**Examples Used:**
- PC (Personal Computer)  
- Laptop  

**Functions:**
- Send and receive data  
- Assigned IP address, subnet mask, and default gateway  
- Used to test connectivity using ping  

---

### 2. Network Devices

#### a) Hub
- Connects multiple PCs  
- Broadcasts data to all connected devices  
- Works at the Physical Layer  

#### b) Switch
- Connects multiple devices in a LAN  
- Forwards data using MAC addresses  
- Reduces collisions  
- Works at the Data Link Layer  

#### c) Bridge
- Connects two LAN segments  
- Filters traffic using MAC addresses  
- Reduces network congestion  

#### d) Router
- Connects different networks  
- Routes data using IP addresses  
- Works at the Network Layer  
- Enables inter-network communication  

#### e) Repeater
- Regenerates weak signals  
- Extends network distance  
- Works at the Physical Layer  

---

### 3. Cables and Connections
Cisco Packet Tracer provides virtual cables.

**Used Cables:**
- Straight-through cable (PC to Switch)  
- Crossover cable (Switch to Router)  
- Console cable (for device configuration)  

---

### 4. IP Addressing
Each device is configured with:
- IP Address  
- Subnet Mask  
- Default Gateway  

This ensures proper communication between devices.

---

## PROCEDURE
1. Open Cisco Packet Tracer on the computer.  
2. Drag and place required network devices (PC, Hub, Switch, Router, etc.) into the workspace.  
3. Connect devices using appropriate network cables.  
4. Assign IP address, subnet mask, and default gateway to each PC.  
5. Configure router interfaces with proper IP addresses.  
6. Save the network configuration.  
7. Use the `ping` command to test communication.  
8. Observe data transmission results.  

---

## OBSERVATION

### HUB SIMULATION
PC0 (192.168.1.1) sends data to the hub. The hub broadcasts the data to all connected devices. PC1 (192.168.1.3) receives and accepts the data as the destination, while PC2 (192.168.1.2) ignores it. This shows that a hub sends data to all ports without filtering.

#### Configuration Table

| Device | Interface | IP Address | Subnet Mask |
|------|----------|-----------|-------------|
| PC0 | FastEthernet0 | 192.168.1.1 | 255.255.255.0 |
| PC1 | FastEthernet0 | 192.168.1.3 | 255.255.255.0 |
| PC2 | FastEthernet0 | 192.168.1.2 | 255.255.255.0 |

**Ping:** PC0 → PC1  

---

### SWITCH SIMULATION
PC3 (192.168.1.1) sends data to the switch. The switch checks its MAC address table and forwards the data only to PC5 (192.168.1.3). PC4 (192.168.1.2) does not receive the data. This reduces unnecessary traffic.

#### Configuration Table

| Device | Interface | IP Address | Subnet Mask |
|------|----------|-----------|-------------|
| PC3 | FastEthernet0 | 192.168.1.1 | 255.255.255.0 |
| PC4 | FastEthernet0 | 192.168.1.2 | 255.255.255.0 |
| PC5 | FastEthernet0 | 192.168.1.3 | 255.255.255.0 |

**Ping:** PC3 → PC5  

---

### BRIDGE SIMULATION
PC6 (192.168.1.1) sends data through the left switch to the bridge. The bridge checks the destination MAC address and forwards the data only to the right network segment. The right switch then delivers the data to PC11 (192.168.1.6). Other PCs do not receive the data.

#### Configuration Table

| Device | IP Address | Subnet Mask |
|------|-----------|-------------|
| PC6 | 192.168.1.1 | 255.255.255.0 |
| PC7 | 192.168.1.2 | 255.255.255.0 |
| PC8 | 192.168.1.3 | 255.255.255.0 |
| PC9 | 192.168.1.4 | 255.255.255.0 |
| PC10 | 192.168.1.5 | 255.255.255.0 |
| PC11 | 192.168.1.6 | 255.255.255.0 |

**Ping:** PC6 → PC9  

---

### ROUTER SIMULATION
PC12 (192.168.1.1) sends data to PC17 (10.0.0.4). Since the destination is on a different network, the data is forwarded to the default gateway (192.168.1.1). The router checks its routing table and forwards the packet to the 10.0.0.0 network via interface 10.0.0.1.

#### Configuration Table

| Device | Default Gateway | IP Address | Subnet Mask |
|------|----------------|-----------|-------------|
| PC12 | 192.168.1.1 | 192.168.1.2 | 255.255.255.0 |
| PC13 | 192.168.1.1 | 192.168.1.3 | 255.255.255.0 |
| PC14 | 192.168.1.1 | 192.168.1.4 | 255.255.255.0 |
| PC15 | 10.0.0.1 | 10.0.0.2 | 255.0.0.0 |
| PC16 | 10.0.0.1 | 10.0.0.3 | 255.0.0.0 |
| PC17 | 10.0.0.1 | 10.0.0.4 | 255.0.0.0 |

**Ping:** PC12 → PC17  

---

### REPEATER SIMULATION
PC0 (192.168.1.1) sends data through Hub1 to the repeater. The repeater regenerates and amplifies the signal and forwards it to Hub2. Hub2 broadcasts the data, and PC5 (192.168.1.6) receives it as the destination. This shows that a repeater works at the physical layer and does not filter data.

#### Configuration Table

| Device | IP Address | Subnet Mask |
|------|-----------|-------------|
| PC0 | 192.168.1.1 | 255.255.255.0 |
| PC1 | 192.168.1.2 | 255.255.255.0 |
| PC2 | 192.168.1.3 | 255.255.255.0 |
| PC3 | 192.168.1.4 | 255.255.255.0 |
| PC4 | 192.168.1.5 | 255.255.255.0 |
| PC5 | 192.168.1.6 | 255.255.255.0 |

**Ping:** PC0 → PC5  

---

## DISCUSSION
The simulation showed successful communication within the same network and between different networks using a router. Switches reduced traffic by forwarding data only to intended devices. Routers enabled inter-network communication, and repeaters maintained signal strength. Proper IP addressing and routing ensured smooth data transmission without packet loss.

---

## CONCLUSION
The simulation of network devices using Cisco Packet Tracer was successfully completed. The experiment demonstrated the working of hubs, switches, bridges, routers, and repeaters. Communication within and between networks was achieved efficiently, fulfilling all the objectives of the lab.

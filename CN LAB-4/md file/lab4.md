# LAB 4: Subnetting and Supernetting using Cisco Packet Tracer

##  Objectives
- Understand the concepts of **Subnetting** and **Supernetting**
- Learn efficient **IP address management**
- Implement subnetting and supernetting using **Cisco Packet Tracer**
- Analyze how these techniques improve **routing and network performance**

---

##  Tools and Software Used
- Cisco Packet Tracer  
- PC with Windows / Linux OS  

---

##  Theory

### 1. Subnetting
Subnetting is the process of dividing a large IP network into smaller logical networks called **subnets**. It improves IP address utilization, reduces network congestion, and enhances security and performance.

#### Working of Subnetting
Subnetting works by borrowing bits from the **host portion** of an IP address and adding them to the **network portion**. This increases the number of networks while reducing hosts per subnet. Each subnet has:
- Network Address  
- Broadcast Address  
- Valid Host Range  

#### Applications of Subnetting
- Dividing organizational networks (HR, IT, Finance, etc.)
- Efficient IP allocation by ISPs
- Improved network security
- Reduced broadcast traffic
- Enterprise and campus networks

---

### 2. Supernetting
Supernetting is the process of combining multiple smaller networks into a single larger network called a **supernet**. It reduces routing table size and improves routing efficiency.

#### Working of Supernetting
Supernetting works by borrowing bits from the **network portion** and adding them to the **host portion**. Multiple contiguous networks are summarized into a single route using a shorter subnet mask.

#### Applications of Supernetting
- Route summarization
- Reduced routing table size
- Improved routing performance
- ISP network management
- Backbone and WAN networks

---

##  Procedure

### Subnetting in Cisco Packet Tracer
1. Open Cisco Packet Tracer  
2. Add routers, switches, and PCs  
3. Assign IP addresses based on subnet table  
4. Configure router interfaces  
5. Set default gateway on PCs  
6. Verify connectivity using `ping`

### Supernetting in Cisco Packet Tracer
1. Create multiple networks  
2. Configure static or dynamic routing  
3. Apply route summarization  
4. Verify routing table and connectivity  

---

##  Network Design

### Subnet Calculation
- **Base Network:** `192.168.1.0/24`
- **Required Subnets:** 4
- **Block Size:** 64 IPs
- **Subnet Mask:** `255.255.255.192` (`/26`)
- **Borrowed Bits:** 2 → `2² = 4 subnets`

#### Subnet Table

| Subnet | Network ID       | Broadcast Address | First Usable IP | Last Usable IP |
|------|------------------|------------------|----------------|---------------|
| 1 | 192.168.1.0   | 192.168.1.63  | 192.168.1.1 | 192.168.1.62 |
| 2 | 192.168.1.64  | 192.168.1.127 | 192.168.1.65 | 192.168.1.126 |
| 3 | 192.168.1.128 | 192.168.1.191 | 192.168.1.129 | 192.168.1.190 |
| 4 | 192.168.1.192 | 192.168.1.255 | 192.168.1.193 | 192.168.1.254 |

---

##  Network Topology

### Subnetting Topology
- Router0 connects two subnets
- Switch0 → PC0, PC1, PC2  
- Switch1 → PC3, PC4, PC5  

#### Configuration Table (Subnetting)

| Device | IP Address | Subnet Mask | Default Gateway |
|------|-----------|------------|----------------|
| Router0 (Fa0/0) | 192.168.1.1 | 255.255.255.192 | N/A |
| Router0 (Fa0/1) | 192.168.2.60 | 255.255.255.192 | N/A |
| PC0 | 192.168.1.2 | 255.255.255.192 | 192.168.1.1 |
| PC1 | 192.168.1.3 | 255.255.255.192 | 192.168.1.1 |
| PC2 | 192.168.1.4 | 255.255.255.192 | 192.168.1.1 |
| PC3 | 192.168.2.61 | 255.255.255.192 | 192.168.2.60 |
| PC4 | 192.168.2.62 | 255.255.255.192 | 192.168.2.60 |
| PC5 | 192.168.2.63 | 255.255.255.192 | 192.168.2.60 |

---

### Supernetting Topology
- One router, one switch, four PCs

#### Configuration Table (Supernetting)

| Device | IP Address | Subnet Mask | Default Gateway |
|------|-----------|------------|----------------|
| Router0 (Fa0/0) | 192.168.0.1 | 255.255.252.0 | N/A |
| PC6 | 192.168.0.10 | 255.255.252.0 | 192.168.0.1 |
| PC7 | 192.168.1.10 | 255.255.252.0 | 192.168.0.1 |
| PC8 | 192.168.2.10 | 255.255.252.0 | 192.168.0.1 |
| PC9 | 192.168.3.10 | 255.255.252.0 | 192.168.0.1 |

---

##  Precautions
1. Verify IP addresses and subnet masks carefully  
2. Ensure routers are configured properly  
3. Avoid overlapping IP ranges  
4. Test connectivity using `ping`  
5. Save Packet Tracer files frequently  

---

##  Discussion
Subnetting divides large networks into smaller segments for better performance and security. Supernetting simplifies routing by combining multiple networks. Cisco Packet Tracer allows easy implementation and verification of these concepts using IP configuration and routing.

---

##  Result
- Devices within the same subnet communicated successfully  
- Inter-subnet communication worked via router  
- Supernetting reduced routing table entries  
- Ping and routing table verification confirmed correct setup  

---

## Conclusion
Subnetting improves network efficiency and management, while supernetting optimizes routing. Cisco Packet Tracer is an effective tool for learning and testing these concepts. Proper implementation ensures scalable and high-performance networks.

---

 **Course:** Computer Networks  
 **Lab:** Subnetting & Supernetting  

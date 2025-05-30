# 📦 DHCP Server Configuration Lab

In this lab, I configured **DHCP pools** for different VLANs, created **excluded address ranges** for critical services like printers and gateways, and assigned proper DNS and default routers for each subnet.

---

## ✅ Objective
- Configure DHCP pools for various VLANs
- Exclude critical IP ranges for static devices
- Set default gateways and DNS for each VLAN

---

## 🌐 Network Breakdown

Each VLAN was configured with its own DHCP pool. Excluded address ranges were reserved for gateways, printers, and servers to avoid IP conflicts. The pools are as follows:

- **VLAN 10 (Finance):** 10.10.65.0/26
- **VLAN 20 (Sales):** 10.10.65.64/26
- **VLAN 30 (HR):** 10.10.65.128/26
- **VLAN 40 (Management):** 10.10.65.192/29
- **VLAN 99 (Network Admin):** 10.10.65.224/29
- **VLAN 60 (Guest):** 10.10.65.240/29

### 🖥️ Topology Diagram

![DHCP Lab Topology](images/DHCP_Topology.png)

This diagram illustrates the device layout per VLAN and their connection to the central switch on Floor 6B.

---

## ⚙️ DHCP Pools Configuration

![DHCP Pools](images/DHCP_Pools.png)

---

## 🚫 Excluded Address Ranges

![Excluded Ranges](images/DHCP_Exclusions.png)

---

### DHCP Parameter Explanation

- **`ip dhcp excluded-address`:** Prevents certain IP addresses from being assigned via DHCP, usually for static devices like gateways or servers.  
- **`network`:** Defines the subnet range for the DHCP pool.  
- **`default-router`:** Sets the default gateway IP clients use to send traffic outside their subnet.  
- **`dns-server`:** Specifies the DNS server IP addresses clients will use to resolve domain names.


## 📝 Notes

DHCP Pool Command: Sorry for the cutoff in the DHCP pool command for the guest VLAN. The complete command is:

network 10.10.65.240 255.255.255.248

default-router 10.10.65.241 

dns-server 10.10.65.242

DHCP Exclusions: Only three IP addresses are excluded from the DHCP pool because this subnet is small and part of the guest VLAN. Since we don’t know how many guests will connect each day, the network uses NAT to simplify IP management—allowing all guests to share one private IP before being translated to a public IP. This approach makes it easier to manage limited IP addresses while avoiding conflicts.


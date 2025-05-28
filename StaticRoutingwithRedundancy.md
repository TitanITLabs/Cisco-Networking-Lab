# 🛣️ Static Routing with Redundancy Lab

In this lab, I configured **static routes** for a network with 8 floors. Each floor has a primary and a secondary route to ensure redundancy in case of gateway failure.

---

## ✅ Objective

- Set up static routes for each floor
- Implement a primary and backup route
- Use `ip route` to simulate failover routing
- Enable SSH access on the router

---

## 🧱 Network Design

- Floors: 8 (Each on different subnets)
- Redundancy: Primary and backup gateways per subnet
- Routers:
  - `192.168.70.1` – Primary route
  - `192.168.65.2` – Secondary/backup route

---

## ⚙️ Configuration Snippet

```plaintext
ip route 10.10.10.0 255.255.255.0 192.168.70.1
ip route 10.10.10.0 255.255.255.0 192.168.65.2 5
ip route 10.10.15.0 255.255.255.0 192.168.70.1
ip route 10.10.15.0 255.255.255.0 192.168.65.2 5
...
ip route 10.10.80.0 255.255.255.0 192.168.70.1
ip route 10.10.80.0 255.255.255.0 192.168.65.2 5

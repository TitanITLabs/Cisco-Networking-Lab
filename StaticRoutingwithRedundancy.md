# 🛣️ Static Routing with Redundancy Lab

In this lab, I configured **static routes** for a network with 8 floors. Each floor has a primary and a secondary route to ensure redundancy in case of gateway failure.

---

## ✅ Objective

- Set up static routes for each floor
- Implement a primary and backup route
- Use `ip route` to simulate failover routing

---

## 🧱 Network Design

- Floors: 8 (Each on different subnets)
- Redundancy: Primary and backup gateways per subnet
- Routers:
  - `192.168.70.1` – Primary route
  - `192.168.65.2` – Secondary/backup route

---

##  🗺️ Topology
![Topology Image](images/Topology.png)

## ⚙️ Configuration

Below is the  upstream static routing configuration used in this lab, including primary and backup routes for all 8 floors:

![Static Routes](images/IpRouting.png)

## 📝 Notes

- I was assigned **Floor 6B**, so I configured static routes **upstream and downstream** starting from my floor.
- For my configuration, the **primary gateway** was `192.168.70.1`, and the **backup** was `192.168.65.2` for upstream routing.
- I do **not have access to the switch anymore**, so I couldn't document the downstream routes (where the backup becomes primary and vice versa).
- In the topology diagram, some floors such as **Floor 4B** are shown but were **not configured** in the actual switch configuration, as they were removed from the final setup due to students withdrawls from class.

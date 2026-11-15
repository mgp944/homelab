
---
Works as the main DNS server, it contains the name resolution to each service on the [[LAN 2]] and [[LAN 3]].
## 🛠️ Hardware Resources 

| Parámetro   | Configuración            |
| :---------- | :----------------------- |
| **ID LXC**  | `CT 100`                 |
| **OS**      | Debian 12 / Ubuntu 24.04 |
| **vCPU**    | 1 Core(s)                |
| ** RAM**    | 2000 MB                  |
| **Storage** | 4 GB (SSD)               |

---

## 🌐 Network Configuration


* **Interfaces:** `eth0` briged to `vmbr1` for [[LAN2]] 
* **IP Address:** `192.168.2.2/24` (Static)  
* **Gateway:** `192.168.2.1`


* **Interfaces:** `eth1` bridgeed to `vmbr2` for [[LAN3]]
* **IP Address:** 192.168.3.2/24` (Static) 
* **Gateway:** `192.168.3.1`

---

## 🔐 Hardening and Security

* **Access SSH:** Disallowed for all the users

---

## 💾 Backup 

> [!warning]
**Proxmox Replication:** **Disabled (Infeasible due to space constraints).**
The current local/remote storage does not meet the minimum quota required to support the disk size of this VM.

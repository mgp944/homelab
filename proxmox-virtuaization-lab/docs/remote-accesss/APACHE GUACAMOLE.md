
---
Remote conection to LAN2 and LAN3 VMs and LXCs.
## 🛠️ Hardware Resources 

| Parámetro   | Configuración            |
| :---------- | :----------------------- |
| **ID LXC**  | `CT 100`                 |
| **OS**      | Debian 12 / Ubuntu 24.04 |
| **vCPU**    | 1 Core(s)                |
| ** RAM**    | 2 GB                     |
| **Storage** | 4 GB (SSD)               |

---

## 🌐 Network Configuration


* **Interfaces:** `eth0` briged to `vmbr1` for [[LAN2]] 
* **IP Address:** `192.168.2.4/24` (Static)  
* **Gateway:** `192.168.2.1`
- **DNS**: 192.168.2.2

* **Interfaces:** `eth1` bridgeed to `vmbr2` for [[LAN3]]
* **IP Address:** 192.168.3.4/24` (Static) 
* **Gateway:** `192.168.3.1`

---

## 🔐 Hardening and Security

* **Access SSH:** Disallowed for all the users

---

## 💾 Backup 

> [!warning]
**Proxmox Replication:** **Disabled (Infeasible due to space constraints).**
The current local/remote storage does not meet the minimum quota required to support the disk size of this VM.

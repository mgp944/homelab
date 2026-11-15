
---
Monitors Internet, VMs and LXCs status in LAN2
## 🛠️ Hardware Resources 

| Parámetro   | Configuración |
| :---------- | :------------ |
| **ID LXC**  | `CT 119`      |
| **OS**      | Debian 12     |
| **vCPU**    | 1 Core(s)     |
| ** RAM**    | 512 GB        |
| **Storage** | 4 GB (SSD)    |

---

## 🌐 Network Configuration


* **Interfaces:** `eth0` briged to `vmbr1` for [[LAN2]] 
* **IP Address:** `192.168.2.7/24` (Static)  
* **Gateway:** `192.168.2.1`
- **DNS**: 192.168.2.2

---
# 📡 Monitoring Configuration

| Asset          | Status Checking | Host        |
| -------------- | --------------- | ----------- |
| [[PIHOLE]]     | via Ping        | 192.168.2.2 |
| [[VM OpenWRT]] | via Ping        | 192.168.2.1 |
| INITERNET      | via Ping        | 8.8.8.8     |

![](Pasted_image_20261103190018.png)

---

## 🔐 Hardening and Security

* **Access SSH:** Disallowed for all the users

---

## 💾 Backup 

> [!warning]
**Proxmox Replication:** **Disabled (Infeasible due to space constraints).**
The current local/remote storage does not meet the minimum quota required to support the disk size of this VM.


---
# Description

Works as a Terminal Server to access via  [[APACHE GUACAMOLE]] to the company's network. 

---

## 🛠️ Hardware Resources 
Detalle del aprovisionamiento asignado en el clúster de Proxmox VE.

| Device            | Parameter          |
| ----------------- | ------------------ |
| RAM               | 2 GB               |
| OS                | Debian 12 Bookworm |
| Storage           | 32 GB              |
| Network Interface | wmbr1              |
| VLAN              | 3                  |
| IP                | DHCP               |

## 🌐 Network Configuration


* **Interfaces:** `eth0` briged to `vmbr1` for [[LAN4]]
* **IP Address:** `192.168.3.` (Static)  
* **Gateway:** `192.168.3.1`
-  **DNS**: 192.168.3.2


---


# Backup 

> [!warning]
**Proxmox Replication:** **Disabled (Infeasible due to space constraints).**
The current local/remote storage does not meet the minimum quota required to support the disk size of this VM.


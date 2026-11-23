
---
Remote conection to LAN2 and LAN3 VMs and LXCs.
## 🛠️ Hardware Resources 

| Parámetro   | Configuración            |     |
| :---------- | :----------------------- | --- |
| **ID LXC**  | `CT 100`                 |     |
| **OS**      | Debian 12 / Ubuntu 24.04 |     |
| **vCPU**    | 1 Core(s)                |     |
| ** RAM**    | 2 GB                     |     |
| **Storage** | 4 GB (SSD)               |     |

---

## 🌐 Network Configuration


* **Interfaces:** `eth0` briged to `vmbr1` for [[LAN2]] 
* **IP Address:** `192.168.2.4/24` (Static)  
* **Gateway:** `192.168.2.1`
- **DNS**: 192.168.2.2

* **Interfaces:** `eth1` bridged to `vmbr2` for [[LAN3]]
* **IP Address:** 192.168.3.4/24` (Static) 
* **Gateway:** `192.168.3.1`

---

## Connections

Actually only one connection is available to the TS Debian based VM via RDP. 


---
## 🔐 Hardening and Security

* **Access SSH:** Disallowed for all the users
* **2FA**: is activated for user access.
* **Limit Logins Attempts**: the instance has the "auth-ban" extension enabled, limiting the login attempts to 5. The user must wait 5 minutes to re-login. (See: https://guacamole.apache.org/doc/1.6.0/gug/auth-ban.html)

![](Pasted%20image%2020261123165348.png)

---

## 💾 Backup 

> [!warning]
**Proxmox Replication:** **Disabled (Infeasible due to space constraints).**
The current local/remote storage does not meet the minimum quota required to support the disk size of this VM.

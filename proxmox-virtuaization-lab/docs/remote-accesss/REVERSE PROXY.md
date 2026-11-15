
---

Reverse proxy to WebGUI of some services, implemented in NGINX PROXY MANAGER. The OpenWRT Router has a fordward rule for each http request to be fordarded to this proxy.
## 🛠️ Hardware Resources 

| Parámetro   | Configuración |
| :---------- | :------------ |
| **ID LXC**  | `CT 116`      |
| **OS**      | Debian 12     |
| **vCPU**    | 2 Core(s)     |
| ** RAM**    | 2 GB          |
| **Storage** | 7 GB (SSD)    |

---

## 🌐 Network Configuration


* **Interfaces:** `eth0` briged to `vmbr1` for [[LAN1]] 
* **IP Address:** `192.168.2.3/24` (Static)  
* **Gateway:** `192.168.2.1`
- **DNS**: 192.168.2.2
- Exposed Ports:
	- 80
---


# Reverse Proxy Rules

Next there are some proxy rules as example.

![[Pasted image 20261103192849.png|700]]

## 🔐 Hardening and Security

* **Access SSH:** Disallowed for all the users

---

## 💾 Backup 

> [!warning]
**Proxmox Replication:** **Disabled (Infeasible due to space constraints).**
The current local/remote storage does not meet the minimum quota required to support the disk size of this VM.

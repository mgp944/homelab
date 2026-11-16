
---

#  Description

Windows IOT version as client machine. Due lack of hadware resources inside PVE, this version was used as example.

## 🛠️ Hardware Resources 


| Parameter | Configurtion           |
| :-------- | :--------------------- |
| **ID VM** | `vm 123`               |
| SO        | Windows IOT Enterprise |
| vCPU      | 2 Core                 |
| RAM       | 2 GB                   |
| Storage   | 20 GB                  |

## 🌐 Network Configuration
Detalles de conectividad y direccionamiento del contenedor.

* **Interface:** `eth0` connected to Home LAN (simulating Internet)
* **IP Address:**  (DHCP)
* **(Default Gateway:** `192.168.2.1`
* **DNS**: 192.168.2.180

# VM Configuration

### Adding to DC: **dc.lab.local**

![](media/Pasted_image_20261110122206.png)

## 🔐 Hardening and Security

* **Access SSH:** Disallowed for all the users

## 💾 Backup 

> [!warning]
**Proxmox Replication:** **Disabled (Infeasible due to space constraints).**
The current local/remote storage does not meet the minimum quota required to support the disk size of this VM.

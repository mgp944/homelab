

---

# 🛠️ Hardware Resources 

| Parameter  | Configurtion |
| :--------- | :----------- |
| **ID LXC** | `CT 104`     |
| SO         | Debian 12    |
| vCPU       | 2 Core       |
| RAM        | 2 GB         |
| Storage    | 20 GB        |

---
## 🌐 Network Configuration

* **Interface:** `eth0` connected to Home LAN
* **IP Address:** `192.168.2.12/24` (Static)
* **(Gateway:** `192.168.2.1`
* **DNS** : 192.168.2.2
* **Exposed Ports:**
	* 80 for WebGUI behind Reverse Proxy

---
# Dashboards Examples

Different dashboard are displayed fot the next data. 

[[Termometer]]: 
* Ambience temperature
* When the temperature reaches to 20°C a message is sent to a private server in [[DISCORD]] as a warning.

[[PVE]]:
The next data are visualized:
	- Total PVE  %CPU used. 
	- Total  %RAM used.
	- Total  %HDD used.
- A message is triggered to [[DISCORD]]  if:
	- %CPU utilization is above to  90%
	- %RAM utilization is above  to 95%
	- %HDD utilization is above to  80%

#todo Agregar Imagenes
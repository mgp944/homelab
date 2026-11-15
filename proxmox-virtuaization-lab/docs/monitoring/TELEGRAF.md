
 ---
It takes the data flux from  [[Termometer]] then it resends the data to an  [[INFLUXDB]] instance. 
The data are received vía [[MODBUS]] which is a standart industry protocol


## 🛠️ Hardware Resources 


| Parameter  | Configurtion |
| :--------- | :----------- |
| **ID LXC** | `CT 104`     |
| SO         | Debian 12    |
| vCPU       | 1 Core       |
| RAM        | 512 MB       |
| Storage    | 5 GB         |


## 🌐 Network Configuration
Detalles de conectividad y direccionamiento del contenedor.

* **Interface:** `eth0` connected to Home LAN (simulating Internet)
* **IP Address:** `192.168.1.106/24` (Static)
* **(Gateway:** `192.168.1.1`
* **Exposed Ports:**
  *

* **Interface:** `eth1` connected to VLAN
* **IP Address:** `192.168.2.22/24` (IP Estática asignada por Proxmox / Reserva DHCP).
* **(Gateway:** `192.168.2.1`
* **Exposed Ports:**
  * 8086 (TCP) - To [[INFLUXDB]] instance.
  
# Configuration Details

```yaml
```



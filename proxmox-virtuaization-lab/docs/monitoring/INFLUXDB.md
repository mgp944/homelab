
---
# Description

Stores temporal series data from diferents devices on the network. The data is finaly sent to a [[GRAFANA]] instance where diferents dashboards are displayed.

## 🛠️ Hardware Resources 

| Device            | Parameter    |
| ----------------- | ------------ |
| **ID LXC**        | `CT 101`     |
| RAM               | 1 GB         |
| Processor         | 2 cores      |
| Storage           | 20 GB        |
| Network Interface | vmr0         |
| Network Address   | 192.168.2.13 |
| Default Gateway   | 192.168.2.1  |
| OS                | Debian 12    |
| DNS               | 192.168.2.2  |

#  Database Configuration

| Bucket         | Stored Information           |
| -------------- | ---------------------------- |
| [[Termometer]] | Ambience Temperature         |
| PVE Bucket     | PVE CPU, HDD and RAM status. |

# Backup 

> [!warning]
**Proxmox Replication:** **Disabled (Infeasible due to space constraints).**
The current local/remote storage does not meet the minimum quota required to support the disk size of this VM.

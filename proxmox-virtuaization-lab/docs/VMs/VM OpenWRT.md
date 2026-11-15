
---

Works as the main router for [[VLAN 2]]

# VM Configuration

| Device            | Parameter     |
| ----------------- | ------------- |
| RAM               | 256 MB        |
| Processor         | 1 Core        |
| Storage           | 2 GB          |
| Network Interface | vmr0          |
| Network Address   | 192.168.1.100 |
| Network Interface | vmr1          |
| Network Address   | 192.168.2.1   |
| Tag               | 2             |

---
# Security

## Fordwarded Ports

| Service Destination   | Ext.Port | Internal IP  | Int, Port | Type | Mechanism | Allowed Sources |
| --------------------- | -------- | ------------ | --------- | ---- | --------- | --------------- |
| Reverse Proxy Web GUI | 81       | 192.168.2.3  | 81        | TCP  | DNAT      | LAN Only        |
| Reverse Proxy         | 80       | 192.168.2.3  | 80        | TCP  | DNAT      | LAN Only        |
| [[INFLUXDB]]          | 8084     | 192.168.2.13 | 8086      | TCP  | DNAT      | LAN Only        |


----

# Backup 

> [!warning]
**Proxmox Replication:** **Disabled (Infeasible due to space constraints).**
The current local/remote storage does not meet the minimum quota required to support the disk size of this VM.

# Exposed Services

>[!Danger] Exposed Services
>None of the services are exposed to the internet. The only way to access them from outside is via Tailscale VPN.

---

# Description

The simulated emviroment is composed by 2 VLANS created in the cluster. The first one has a [[OpenWRT]] virtualized router and the second one has a [[VyOS]] virtualized router. 

## Topology

```mermaid
flowchart TB
    SENSOR["Thermometer"]
    HOME["Home LAN"]

    subgraph PVE["Proxmox VE"]
        subgraph WAN["vmbr0"]
            OW_WAN["OpenWrt WAN"]
        end

        subgraph ROUTER["OpenWrt"]
            OW_FW["Firewall / NAT"]
        end

        subgraph LAN["vmbr1 — OpenWrt LAN"]
            TLG["LXC — Telegraf"]
            SERVICES["Other services"]
            NGINX["Nginx Reverse Proxy"]
        end
    end

    HOME --> OW_WAN
    OW_WAN --> OW_FW
    OW_FW -->|"DNAT TCP 2910"| TLG
    OW_FW --> NGINX
    NGINX --> SERVICES
    SENSOR -->|"Modbus TCP"| OW_FW

```
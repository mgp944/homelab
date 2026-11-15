# Home lab - Infrastructure & Virtualization

Personal home lab. 

# Objetives

* Learn about Proxmox usage.
	* VM hardware assignment.
	* Network structure and connections
	* Basic backup and storage management.
* Learn about virtualization management.
* Learn about Software Defined Network for virtualized machines.
* Learn about virtualized router OS  implementations. 
* Implement and manage a home lab, simulating an small enterprise environment.
## Diagram

### VMs and LXCs

![](network_diagram.png)

## Technologies

- Proxmox VE
- LXC
- OpenWRT
- VyOS
- Linux
- Telegraf
- InfluxDB
- Grafana
- Tailscale (VPN)
- NGINX Reverse Proxy

## Objectives

- Virtualization experiment
- Monitoring implementation
- Data acquisition simulation
- Practice troubleshooting

# Hardware

- Dell PowerEdge R210 II: host del PVE.
- Router TP-LINK TL-WR941ND: configured as bridge to home LAN and the server.
- ESP8266: as thermometer.

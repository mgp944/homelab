
The data is created by ESP8266 temperature sensing, the data is handled at the end by a [[GRAFANA]] dashboard. The measurements are stored in a temporal series database implemented via [[INFLUXDB]]. The bucked is called Weather
 
```mermaid

flowchart LR

esp["ESP8286"]
wifi["Home WI-FI"]
subgraph VLAN2
	openwrt["OpenWRT"]
	telegraf["Telegraf LXC"]
	influx[("Influx Bucket")]
	grafana["Grafana"]
	PVE["PVE sensors"]
end

esp --> wifi --> openwrt --> influx --> grafana
PVE --> telegraf --> influx 


style VLAN2 border:#81f,stroke:#243,stroke-width:4px
style esp border:#fef,stroke:#243,stroke-width:4px
```


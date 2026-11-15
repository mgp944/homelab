
The data is created by ESP8266 temperature sensing, the data is handled at the end by a [[GRAFANA]] dashboard. The measurements are stored in a temporal series database implemented via [[INFLUXDB]]. The bucked is called ___
A [[TELEGRAF]] instances was used to centralize future data collection from different sources 
 
```mermaid

flowchart LR

esp["ESP8286"]
wifi["WI-FI"]
subgraph VLAN2
openwrt["OpenWRT"]
telegraf["Telegraf LXC"]
influx[("Influx Bucket")]
grafana["Grafana"]
end

esp --> wifi --> openwrt --> telegraf --> influx --> grafana


style VLAN2 border:#81f,stroke:#243,stroke-width:4px
style esp border:#fef,stroke:#243,stroke-width:4px
```


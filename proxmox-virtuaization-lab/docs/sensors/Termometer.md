Based on [[ESP8266]] and the LM35. It sends data to an [[INFLUXDB]] instance via [[TELEGRAF]] The communication takes place using the MODBUS protocol.
# Electronic Schema


![[Esp8266_lm35.png]]
# [[ESP8266]] Configuration

| Element      | Value                                                    |
| ------------ | -------------------------------------------------------- |
| Protocol     | TCP                                                      |
| Connectivity | WI-FI                                                    |
| Destinity    | INFLUXDB HOST                                            |
| Port         |                                                          |
| Bucket       |                                                          |
| Auth         | Token                                                    |
| Payload      |                                                          |
| Endpoint     | /api/v2/write?org=ORGANIZATION&bucket=BUCKET&precision=s |



# Implemented Code

```c++


```


Based on [[ESP8266]] and the LM35. It sends data to an [[INFLUXDB]] instance via [[TELEGRAF]] The communication takes place via TCP using the Influx Client Library.
# Electronic Schema


![[Esp8266_lm35.png]]
# [[ESP8266]] Configuration

| Element      | Value         |
| ------------ | ------------- |
| Protocol     | TCP           |
| Connectivity | WI-FI         |
| Destinity    | INFLUXDB HOST |
| Port         | 8084          |
| Bucket       | Weather       |
| Auth         | Token         |

# Implemented Code

The next code is the ESP8286 firmware which pushes data to the InfluxDB instances bucket called Weather


```c++
#include <ESP8266WiFiMulti.h>
#include <InfluxDbClient.h>
#include <Wire.h>

//Network Configuration and Security  
#define WIFI_SSID ""
#define WIFI_PASSWORD ""
#define INFLUXDB_TOKEN ""
#define INFLUXDB_ORG "local"
#define INFLUXDB_BUCKET "weather"
#define INFLUXDB_URL "http://192.168.1.101:8084"

//Temperatur sensing

#define ADC_VREF_mV 3300.0 // in millivolt
#define ADC_RESOLUTION 1024.0
#define PIN_LM35 A0 // The ESP8266 pin ADC0 connected to LM35

  

int counter = 0;
int ledPin = 2;

ESP8266WiFiMulti wifiMulti;

InfluxDBClient client(INFLUXDB_URL, INFLUXDB_ORG, INFLUXDB_BUCKET, INFLUXDB_TOKEN);

Point sensor("temperature");

void setup() {

Serial.begin(115200);

//LED
pinMode(ledPin, OUTPUT);
//Start WIFI
WiFi.begin(WIFI_SSID, WIFI_PASSWORD);

while (WiFi.status() != WL_CONNECTED) {
	
	delay(500);
	
	// Sync time and validate connection
	timeSync("UTC", "pool.ntp.org");
	client.validateConnection();
}

void loop() {

	int adcVal = analogRead(PIN_LM35);
	float milliVolt = adcVal * (ADC_VREF_mV / ADC_RESOLUTION);
	float temperature_C = milliVolt / 10;
	float temperature_F = temperature_C * 9 / 5 + 32;
	
	sensor.clearFields();
	
	sensor.addField("temp_c", temperature_C);
	
	client.writePoint(sensor);
}

```

# Security

The ESP8286 is connected to a private Wi-Fi access point placed in the home network. The authentication against the InfluxDB bucket is made via token. 
A forwarded port was used to connect to the database in the OpenWrt instance.
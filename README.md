# home-assistant-tong-petronas-weight-scale
home assistant tong petronas weight scale


nodemcu + hx711 + 150kg load cell + ds18b20

# Component
![image](https://user-images.githubusercontent.com/63136346/234551543-9d91a1eb-098c-44b9-a607-453c5fc50a25.png)

1. nodemcu - rm9

https://shopee.com.my/Wireless-module-CH340-CH340G-NodeMcu-V3-Lua-WIFI-Internet-of-Things-development-board-based-ESP8266-i.110910897.5306533860

2. 150kg load cell - rm33

https://shopee.com.my/150KG-180KG-200kg-220KG-electronic-platform-scale-load-cell-pressure-balanced-cantilever-load-i.37988701.18725023887
![image](https://user-images.githubusercontent.com/63136346/234546371-478ccb44-5652-40d2-93b7-9651d2b56cd1.png)

3. Hx711 - rm3

https://shopee.com.my/Mini-HX711-Weighing-Sensor-Dual-Channel-24-Bit-Precision-A-D-Module-Pressure-Sensor-Microcontroller-i.550994225.10092304576

3. ds18b20 - rm5 x 2

https://shopee.com.my/1M-2M-2.5M-3M-DS18B20-Waterproof-Temperature-Temp-Sensor-Digital-Thermal-Probe-for-arduino-Controller-i.175472467.2839363796

# Setup

# 1. EspHome
    Refer to file: gaspetronas.yaml


# 2. Home assistant lovelace

![image](https://user-images.githubusercontent.com/63136346/234546103-12da242a-89da-41b4-8d72-22b24de7a6bb.png)

     a. Gauge Card Configuration
          type: gauge
          max: 32
          needle: true
          severity:
            green: 24
            yellow: 20
            red: 16
          min: 16
          entity: sensor.gaspetronas_gas_petronas_raw
     b. Entities Card Configuration
        type: entities
          - entity: binary_sensor.gaspetronas_status_dapur_kiri
          - entity: binary_sensor.gaspetronas_status_dapur_kanan
          - entity: sensor.gaspetronas_dapur_kiri
          - entity: sensor.gaspetronas_dapur_kanan
          - entity: sensor.gaspetronas_gas_petronas_raw
            name: Gas Petronas Raw
          - entity: sensor.gaspetronas_petronas_berat_gas_kg
            name: Petronas Berat Gas kg
          - entity: sensor.gaspetronas_petronas_gas_usage_m3
            name: Petronas Gas Usage (m³)
          - entity: sensor.petronas_gas_daily
          - entity: sensor.petronas_gas_monthly
          - entity: sensor.stats_dapurkanan
          - entity: sensor.stats_dapurkiri
        title: gaspetronas

# References
1. Building a bed occupancy sensor for Home Assistant

https://everythingsmarthome.co.uk/building-a-bed-occupancy-sensor-for-home-assistant/?fbclid=IwAR0WeUXlgkAMa_q5WUUfeYlAb3Ml1X4fnHhHRwAMX6VZCuKC6bAkBWexLq8

2. Measure Propane, CO2, Salt, and so much more with this DIY MQTT Weight Sensor using Tasmota

https://www.thesmarthomehookup.com/diy-weight/?fbclid=IwAR2Mbtf7MhSrRkxYHYo8gb3rr5fMSEI-YQkKzr4_YyJPjMiB0ey7T466T7w

3. markusressel ESPHome-Smart-Scale

https://github.com/markusressel/ESPHome-Smart-Scale?fbclid=IwAR3GlpHknn79m6mIvBI3P59OpnZbeBbBWcwsBaEeW_b8cO2CkI4seYPRFuU

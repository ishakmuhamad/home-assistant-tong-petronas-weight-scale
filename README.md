# home-assistant-tong-petronas-weight-scale
home assistant tong petronas weight scale


nodemcu + hx711 + 150kg load cell + ds18b20

# Component
![image](https://user-images.githubusercontent.com/63136346/234551543-9d91a1eb-098c-44b9-a607-453c5fc50a25.png)

1. nodemcu - rm20

https://shopee.com.my/NodeMCU-Lua-V3-ESP8266-WIFI-with-CH340G-i.67321722.1369676742?sp_atk=a8bc2a60-ed80-477d-9139-b589a10a7ea9&xptdk=a8bc2a60-ed80-477d-9139-b589a10a7ea9

2. 150kg load cell - rm33

https://shopee.com.my/150KG-180KG-200kg-220KG-electronic-platform-scale-load-cell-pressure-balanced-cantilever-load-i.37988701.18725023887
![image](https://user-images.githubusercontent.com/63136346/234546371-478ccb44-5652-40d2-93b7-9651d2b56cd1.png)

3. Hx711 - rm6.50

https://shopee.com.my/Load-Cell-Straight-Bar-5kg-1kg-50KG-Weight-Sensor-HX711-module-i.67321722.1170398438?sp_atk=65958100-10b0-4461-ac4f-d4a93a468e1a&xptdk=65958100-10b0-4461-ac4f-d4a93a468e1a

3. ds18b20 - rm7 x 2

https://shopee.com.my/Arduino-Water-Proof-DS18b20-Temperature-Sensor-Probe-i.67321722.1170224467?sp_atk=c74cc895-954b-4821-be3a-3ea9d2e6717b&xptdk=c74cc895-954b-4821-be3a-3ea9d2e6717b
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

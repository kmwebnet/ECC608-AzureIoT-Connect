# ECC608-mqtts-AzureIoT-Connect

This publishies and subscribes Azure IoT hub with IO protection for ECDH premaster secret transmission, which is provided by ATECC608A capability.

# Requirements

  Platformio with VS Code environment.
  install "Espressif 32" platform definition on Platformio  
  Prior to compile this project, you must run [ECC608-AzureDPS-Provision](https://github.com/kmwebnet/ECC608-AzureDPS-Provision) with success result.  
  doing this, Azure IoT Hub connection URL that is needed to connect it will store in ATECC608A EEPROM.

  you need to modify the definition and variables in main.c as follows:  
  ```
// your SSID and PASS
#define EXAMPLE_WIFI_SSID ""
#define EXAMPLE_WIFI_PASS ""

  ```

  and you need to place "cert_chain.c" contents from [ECC608-AzureDPS-Provision](https://github.com/kmwebnet/ECC608-AzureDPS-Provision) with success result.   

# Environment reference
  
  Espressif ESP32-DevkitC
  this project initialize both of I2C 0,1 port, and the device on I2C port 0 is BME280 ambient sensor.
  pin assined as below:


      I2C 0 SDA GPIO_NUM_18
      I2C 0 SCL GPIO_NUM_19

      I2C 1 SDA GPIO_NUM_21
      I2C 1 SCL GPIO_NUM_22
          
  Microchip ATECC608A(on I2C port 1)

# Usage

you need to change a serial port number which actually connected to ESP32 in platformio.ini.

# Result

If you run this project with success, you can find the results on serial console as follows:  
you can confirm by issuing test message to the device from your Azure IoT hub console.  
<img width="780" alt="azureiothub" src="https://user-images.githubusercontent.com/46954791/59815440-8b4a9400-9353-11e9-98c1-58fd6a009cb7.png">

# License

This software is released under the MIT License, see LICENSE.

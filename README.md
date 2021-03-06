Wi-Fi Keylogger with multiple layout support.

**NOTE:** Some keys or modifiers have not been implemented, this is a PoC. I don't have time or material to test all the keyboards.
If you have any errors, you can contact me by Twitter: @JoelSernaMoreno

**Layouts:**

* BE_BE layout support.
* DE_DE layout support.
* ES_ES layout support.
* EN_US layout support.
* FI_FI layout support.
* FR_FR layout support.
* IT_IT layout support.
* PT_PT layout support.
* TR_TR layout support.

**TODO:**
* MORE LAYOUTS
* MORE KEYS
* TEST ALL LAYOUTS

## Configuration:

1. Default IP: 192.168.4.1
2. Default SSID: WiFiKeylogger
3. Default password: hardwareKeylogger
4. Default layout: EN_US

## Hardware requirements:

1. Arduino Pro Micro 3.3V
2. ESP8266-01
3. USB Host

## Pinout:


### Pinout arduino pro micro:


![Pinout arduino pro micro](https://github.com/joelsernamoreno/WiFiKeylogger/blob/master/images/promicro.png)


### Pinout ESP8266-01:


![Pinout arduino pro micro](https://github.com/joelsernamoreno/WiFiKeylogger/blob/master/images/esp8266-01_pinout.jpg)


### Pinout USB host:


![Pinout arduino pro micro](https://github.com/joelsernamoreno/WiFiKeylogger/blob/master/images/usb_host.jpg)


### Pinout ESP8266-01 programming mode:


![Pinout ESP8266-01 programming mode](https://github.com/joelsernamoreno/WiFiKeylogger/blob/master/images/esp8266programmer.PNG)


![ESP8266-01 programming mode breadboard](https://github.com/joelsernamoreno/WiFiKeylogger/blob/master/images/esp_programming_breadboard.jpg)


**Note:** You can also use the pro micro device to program the ESP8266-01 device. In the examples shown here, it has been divided into two circuits so that the user understands the different connections we need to use.


### Pinout WiFi Keylogger:


![Pinout WiFi Keylogger](https://github.com/joelsernamoreno/WiFiKeylogger/blob/master/images/keylogger.PNG)

![Keylogger breadboard](https://github.com/joelsernamoreno/WiFiKeylogger/blob/master/images/keylogger_breadboard.jpg)


## Instalation:


### Software requirements:

1. Download and Install the Arduino IDE: https://www.arduino.cc/en/main/software
2. Go to File - Preferences. Locate the field "Additional Board Manager URLs:" Add "http://arduino.esp8266.com/stable/package_esp8266com_index.json" without quotes. Click "Ok"

If Arduino IDE gives you the following error: "Error downloading http://arduino.esp8266.com/stable/package_esp8266com_index.json" use "https://github.com/esp8266/Arduino/releases/download/2.3.0/package_esp8266com_index.json" instead.

3. Select Tools - Board - Boards Manager. Search for "esp8266". Install "esp8266 by ESP8266 community version 2.3.0". Click "Close".
4. Download/extract WiFiKeylogger repository.
5. Copy the Keyboard and USB Host Shield libraries included in this repository to your Arduino library directory. **NOTE:** The Keyboard library included in this repository has been modified, WiFiKeylogger needs this library to work.

### Programming mode ESP8266-01:


1. Connect the breadboard to the computer with the circuit shown in the esp8266-01 programming mode.
2. Open the ESP8266-01.ino sketch from the source folder.
3. Select Tools - Board - "Generic ESP8266 Module".
4. Select Tools – Upload Speed “115200”.
5. Select Tools – Flash Size “512K (64K SPIFFS)”.
6. Select Sketch - "Export Compiled Binary".
7. Now flash the firmware to the ESP chip using one of the following tools:

**Linux:** https://github.com/AprilBrother/esptool

1. sudo python esptool.py --port=/dev/ttyUSB0 erase_flash
2. sudo python esptool.py --port=/dev/ttyUSB0 --baud 115200 write_flash 0x00000 /home/WiFiKeylogger/ESP8266-01/ESP8266-01.ino.generic.bin --flash_size 32m

**Windows:** https://github.com/nodemcu/nodemcu-flasher

### Upload WifiKeylogger sketch:

1. Connect the breadboard to the computer with the circuit shown in the WiFi Keylogger pinout. 
1. Open the WiFiKeylogger.ino sketch from the source folder.
2. Select Tools - Board – "Arduino Lilypad USB".
3. Select the Port your device is connected to under Tools – Port.
4. Upload the sketch.

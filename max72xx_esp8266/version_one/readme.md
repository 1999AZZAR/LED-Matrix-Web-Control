# MD_MAX72xx WiFi Scrolling Message
This code demonstrates how to use the MD_MAX72xx library to scroll text on the display received through the ESP8266 WiFi interface. The user can enter text through a web browser, and this will display as a scrolling message on the display. The code utilizes the ESP8266WiFi.h library to communicate over WiFi, and the SPI.h library to communicate with the MAX72xx display driver.

## Hardware Required
1. ESP8266 development board
2. MD_MAX72xx-based LED matrix display.
3. Jumper wires

## Library Dependencies
- ESP8266WiFi.h
- SPI.h
- MD_MAX72xx.h

## Pin Connections
Connect the following pins between ESP8266 and MD_MAX72xx display driver.

|ESP8266|MAX7219/MAX7221|
|-------|---------------|
|3V3|Vcc|
|GND|GND|
|D7/MOSI|DATA IN|
|D8/CS|LOAD/CS|
|D5/SCK|CLK|

Note: These pin numbers may need to be changed to match your hardware.

## Usage
1. Connect your ESP8266 development board and the MD_MAX72xx display driver according to the pin connections specified above.
2. Flash the ESP8266 with the code provided.
3. Connect your computer or mobile device to the WiFi network "running text" using the password "12345678".
4. Open a web browser and navigate to the IP address displayed on the LED matrix connected to the ESP8266.
5. Enter a message in the text box, and click the "Send Text" button. The message will begin scrolling on the LED matrix.
6. To enter a new message, repeat step 5.

## Functionality
The code utilizes the callback function to control what is scrolled on the display text. The user can enter text through a web browser, and this will display as a scrolling message on the display. The IP address for the ESP8266 is displayed on the scrolling display after startup initialization and connected to the WiFi network.

The user enters the message in the text box on the web page, and this is sent to the ESP8266 via HTTP GET request. The message is then displayed on the LED matrix as a scrolling message.

The code also contains a heartbeat function that toggles a GPIO pin (D2) on and off. This function is disabled by default and can be enabled by setting the `LED_HEARTBEAT` constant to 1. The `HB_LED_TIME` constant can also be adjusted to change the duration of the heartbeat.

The `DEBUG` constant can be set to 1 to enable debugging messages to the serial console. The `PRINT_CALLBACK` constant can also be set to 1 to print messages related to the callback function to the serial console.

## Credits
The code is based on the Parola_ESP8266_WiFi_Scrolling example included with the MD_MAX72xx library.

The MD_MAX72xx library was created by Mark Stanley and is maintained by MajicDesigns.

The ESP8266WiFi.h library is part of the ESP8266 core for Arduino and was created by Ivan Grokhotkov.

The SPI.h library is part of the Arduino core for ESP8266 and was created by Cristian Maglie, Ivan Grokhotkov, Michael Miller, and Paul Stoffregen.

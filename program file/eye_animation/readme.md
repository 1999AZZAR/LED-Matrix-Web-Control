# Eye Animation

This program is designed to animate a pair of eyes on LED matrix modules using the MD_MAX72XX library. The eyes are coordinated to work together and fill all available matrix modules.

## Dependencies

- ESP8266WiFi library
- MD_MAX72xx library
- SPI library
- MD_EyePair library (included in the code)

## Hardware Setup

- Number of devices in the chain: 2
- Hardware interface type: MD_MAX72XX::PAROLA_HW or MD_MAX72XX::FC16_HW (choose one)
- Pin configuration:
  - CLK_PIN: Connect to the CLK pin of the LED matrix
  - DATA_PIN: Connect to the DATA pin of the LED matrix
  - CS_PIN: Connect to the CS pin of the LED matrix

Note: The pin numbers mentioned in the code might not work with your specific hardware and may need to be adjusted accordingly.

## Initialization and Eye Configuration

1. Create an instance of the MD_MAX72XX class using the chosen hardware interface type, pin configuration, and the number of devices.
2. Create an array of MD_EyePair objects to represent the eyes. The number of eye pairs is determined by dividing the number of devices by 2.
3. Initialize the eye view for each eye pair by calling the `begin()` function with the index of the eye pair, the MD_MAX72XX object, and the delay time between eye movements.

## Main Loop

In the `loop()` function, the `animate()` function is called for each eye pair to animate the eyes on the LED matrix modules.

## Usage

1. Make sure to set up the hardware connections correctly.
2. Install the required libraries mentioned in the dependencies section.
3. Upload the code to your ESP8266 board.
4. Observe the animated eyes on the LED matrix modules.

## flowchart

```mermaid
graph LR
A[Start] --> B[Initialize MD_MAX72XX]
B --> C[Create MD_EyePair objects]
C --> D[Initialize eye view]
D --> E[Animate eyes]
E --> D
```

Note: Adjust the `DELAYTIME` constant to control the speed of the eye animation.

## Contributing

Feel free to contribute to the development of this code by creating pull requests or suggesting improvements.

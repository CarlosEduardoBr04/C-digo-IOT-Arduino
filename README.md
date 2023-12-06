# ⚡ Código-IOT-Arduino

🚨 This repository contains the source code for an RFID card reading system using an MFRC522 module and an LCD display with Arduino. The project enables authentication and reading of data stored on MIFARE cards, displaying the information on the LCD.

## 💻 Resources

### Arduino Components:
1. Arduino Uno R3
2. USB Cable for Arduino
3. LCD 16×2 Display with Blue Backlight
4. RFID Reader Module Kit Mfrc522 Mifare
5. Linear Potentiometer 5KΩ
6. 7 Female Jumper Wires
7. 23 Male Jumper Wires

### Features:
- Reading RFID cards using the MFRC522 module.
- Authentication and reading of data from specific sectors on MIFARE cards.
- Displaying information on the LCD.
- Modular structure for easy expansion and integration.

## > 📖 Instructions:

### > ⚡ Connecting the RFID Module to Arduino:
The wiring diagram for connecting the RFID module to the digital Arduino is the same as for the physical Arduino. The user just needs to bring the card close. Connect the module as shown in the image, noting that its power supply is 3.3V. We will use an LCD display to show the reading message.

### > 🔧 RFID Reader Pinout:
The RFID reader has 8 pins following the following connection sequence. Pay attention to the allowed power supply voltage, which in this case is 3.3 volts.

- Pin SDA connected to pin 10 on Arduino.
- Pin SCK connected to pin 13 on Arduino.
- Pin MOSI connected to pin 11 on Arduino.
- Pin MISO connected to pin 12 on Arduino.
- Pin NC – Not connected.
- Pin GND connected to GND pin on Arduino.
- Pin RST connected to pin 9 on Arduino.
- Pin 3.3 – connected to 3.3V pin on Arduino.

### > 🚨 The pins of the LCD display are connected to the Arduino pins as follows 🚨:
- RS pin of the LCD is connected to digital pin 6 on Arduino.
- E pin of the LCD is connected to digital pin 7 on Arduino.
- D4 pin of the LCD is connected to digital pin 5 on Arduino.
- D5 pin of the LCD is connected to digital pin 4 on Arduino.
- D6 pin of the LCD is connected to digital pin 3 on Arduino.
- D7 pin of the LCD is connected to digital pin 2 on Arduino.

### > 📚 MFRC522 Library:
Load the following program onto the Arduino, which uses the MFRC522 library. Unzip the folder and place it inside the LIBRARIES folder of the Arduino IDE.

The MFRC522 library for Arduino is a software interface that enables communication with the MFRC522 RFID (Radio-Frequency Identification) reader module. This library simplifies the interaction between Arduino and the module, allowing the reading and writing of information on RFID cards.

## > ✨ Main features of the MFRC522 library:

1. **Module Initialization:**
   - The library simplifies the initialization of the MFRC522 module, configuring the communication pins correctly.

2. **Authentication:**
   - Allows authentication for accessing data blocks on RFID cards using authentication keys A or B.

3. **Reading and Writing:**
   - Provides functions to read and write data in specific sectors and blocks of an RFID card.

4. **Card Identification:**
   - The library enables checking the presence of a card and reading its UID (Unique Identifier).

5. **Card Halt:**
   - Allows deactivating communication with a card, rendering it inactive.

6. **Card Type:**
   - Provides information about the type of detected RFID card (e.g., MIFARE Classic, MIFARE Ultralight, etc.).

## > 🚨 Configuration:

- The code is set up to work with the MFRC522 module and an LCD display.
- Ensure to connect the pins correctly according to the definitions in the code.
- Customize the MIFARE authentication key as needed.

  ## 👨‍💻 Author

- [CarlosEduardoBr04](https://github.com/CarlosEduardoBr04)
- [LuizGustavoSouzaAlmeida](https://github.com/LuizGustavoSouzaAlmeida)

## > 📚 Notes:

- This project is a basic implementation and can be expanded to include more features, such as database storage or integration with IoT services.

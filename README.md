# ⚡ Código-IOT-Arduino

---🌐English🌐---

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

  ----- 🌐PT-BR | Português do Brasil🌐 -----

  # ⚡ IoT-Arduino Code

🚨 Este repositório contém o código-fonte para um sistema de leitura de cartões RFID usando um módulo MFRC522 e um display LCD com Arduino. O projeto possibilita autenticação e leitura de dados armazenados em cartões MIFARE, exibindo as informações no LCD.

## 💻 Recursos

### Componentes Arduino:
1. Arduino Uno R3
2. Cabo USB para Arduino
3. Display LCD 16×2 com retroiluminação azul
4. Módulo Leitor RFID Kit Mfrc522 Mifare
5. Potenciômetro Linear 5KΩ
6. 7 Cabos de conexão fêmea
7. 23 Cabos de conexão macho

### Recursos:
- Leitura de cartões RFID usando o módulo MFRC522.
- Autenticação e leitura de dados de setores específicos em cartões MIFARE.
- Exibição de informações no LCD.
- Estrutura modular para fácil expansão e integração.

## > 📖 Instruções:

### > ⚡ Conectando o Módulo RFID ao Arduino:
O diagrama de fiação para conectar o módulo RFID ao Arduino digital é o mesmo do Arduino físico. O usuário só precisa aproximar o cartão. Conecte o módulo conforme mostrado na imagem, observando que sua alimentação é de 3,3V. Vamos usar um display LCD para mostrar a mensagem de leitura.

### > 🔧 Layout do Leitor RFID:
O leitor RFID possui 8 pinos seguindo a sequência de conexão a seguir. Preste atenção na tensão de alimentação permitida, que neste caso é 3,3 volts.

- Pino SDA conectado ao pino 10 no Arduino.
- Pino SCK conectado ao pino 13 no Arduino.
- Pino MOSI conectado ao pino 11 no Arduino.
- Pino MISO conectado ao pino 12 no Arduino.
- Pino NC – Não conectado.
- Pino GND conectado ao pino GND no Arduino.
- Pino RST conectado ao pino 9 no Arduino.
- Pino 3,3 – conectado ao pino 3,3V no Arduino.

### > 🚨 Configuração dos Pinos do Display LCD:
- Pino RS do LCD é conectado ao pino digital 6 no Arduino.
- Pino E do LCD é conectado ao pino digital 7 no Arduino.
- Pino D4 do LCD é conectado ao pino digital 5 no Arduino.
- Pino D5 do LCD é conectado ao pino digital 4 no Arduino.
- Pino D6 do LCD é conectado ao pino digital 3 no Arduino.
- Pino D7 do LCD é conectado ao pino digital 2 no Arduino.

### > 📚 Biblioteca MFRC522:
Carregue o seguinte programa no Arduino, que utiliza a biblioteca MFRC522. Descompacte a pasta e coloque-a dentro da pasta LIBRARIES do Arduino IDE.

A biblioteca MFRC522 para Arduino é uma interface de software que permite a comunicação com o módulo leitor RFID MFRC522. Essa biblioteca simplifica a interação entre o Arduino e o módulo, permitindo a leitura e gravação de informações em cartões RFID.

## > ✨ Principais características da biblioteca MFRC522:

1. **Inicialização do Módulo:**
   - A biblioteca simplifica a inicialização do módulo MFRC522, configurando corretamente os pinos de comunicação.

2. **Autenticação:**
   - Permite autenticação para acessar blocos de dados em cartões RFID usando chaves de autenticação A ou B.

3. **Leitura e Gravação:**
   - Fornece funções para ler e gravar dados em setores e blocos específicos de um cartão RFID.

4. **Identificação do Cartão:**
   - A biblioteca permite verificar a presença de um cartão e ler seu UID (Identificador Único).

5. **Desativação do Cartão:**
   - Permite desativar a comunicação com um cartão, tornando-o inativo.

6. **Tipo de Cartão:**
   - Fornece informações sobre o tipo de cartão RFID detectado (por exemplo, MIFARE Classic, MIFARE Ultralight, etc.).

## > 🚨 Configuração:

- O código está configurado para funcionar com o módulo MFRC522 e um display LCD.
- Certifique-se de conectar os pinos corretamente de acordo com as definições no código.
- Personalize a chave de autenticação MIFARE conforme necessário.

## 👨‍💻 Autor

- [CarlosEduardoBr04](https://github.com/CarlosEduardoBr04)
- [LuizGustavoSouzaAlmeida](https://github.com/LuizGustavoSouzaAlmeida)

## > 📚 Observações:

- Este projeto é uma implementação básica e pode ser expandido para incluir mais recursos, como armazenamento em banco de dados ou integração com serviços de IoT.

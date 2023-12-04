<font color="green"># C-digo-IOT-Arduino</font>


Este repositório contém o código-fonte para um sistema de leitura de cartões RFID utilizando um módulo MFRC522 e um display LCD com Arduino. O projeto permite a autenticação e leitura de dados armazenados em cartões MIFARE, exibindo as informações no LCD.

Recursos:

Componentes Arduino
 1 Arduino Uno R3,
 1 Cabo USB para Arduino,
 1 Display LCD 16×2 Backlight Azul,
 1 Kit Módulo Leitor Rfid Mfrc522 Mifare,
 1 Potenciômetro Linear 5KΩ,
 7 Jumper Femea,
 23 Jumper Macho

Leitura de cartões RFID usando o módulo MFRC522.
Autenticação e leitura de dados de setores específicos nos cartões MIFARE.
Exibição de informações no LCD.
Estrutura modular para fácil expansão e integração.

Instruções:

Ligação do módulo RFID ao Arduino

O esquema de ligação do módulo RFID ao Arduino digital é o mesmo do Arduino Fisico , o usuario apenas vai precisar aproximar o cartão. Conecte o módulo conforme a imagem, observando que a alimentação dele é de 3,3V. Vamos utilizar um display LCD para mostrar a mensagen de leitura

Pinagem Leitor RFID
O leitor RFID tem 8 pinos que seguem a seguinte sequência de ligação. Atenção à tensão de alimentação permitida neste caso é de 3.3 volts

Pino SDA ligado na porta 10 do Arduino
Pino SCK ligado na porta 13 do Arduino
Pino MOSI ligado na porta 11 do Arduino
Pino MISO ligado na porta 12 do Arduino
Pino NC – Não conectado
Pino GND  ligado no pino GND do Arduino
Pino RST ligado na porta 9 do Arduino
Pino 3.3 – ligado ao pino 3.3 V do Arduino

Os pinos do display LCD estão conectados aos pinos do Arduino da seguinte forma

Pino RS do LCD está conectado ao pino digital 6 no Arduino.
Pino E do LCD está conectado ao pino digital 7 no Arduino.
Pino D4 do LCD está conectado ao pino digital 5 no Arduino.
Pino D5 do LCD está conectado ao pino digital 4 no Arduino.
Pino D6 do LCD está conectado ao pino digital 3 no Arduino.
Pino D7 do LCD está conectado ao pino digital 2 no Arduino.

BIBLIOTECA MFRC522

Carregue o seguinte programa no Arduino, que utiliza a biblioteca MFRC522,  Descompacte a pasta e coloque-a dentro da pasta LIBRARIES da IDE do Arduino.

A biblioteca MFRC522 para Arduino é uma interface de software que permite a comunicação com o módulo leitor de RFID (Radio-Frequency Identification) MFRC522. Esta biblioteca facilita a interação entre o Arduino e o módulo, permitindo ler e gravar informações em cartões RFID.

Principais funcionalidades da biblioteca MFRC522:

1-Inicialização do Módulo: A biblioteca facilita a inicialização do módulo MFRC522, configurando os pinos de comunicação corretamente.

2-Autenticação: Permite autenticar o acesso a blocos de dados em cartões RFID usando chaves de autenticação A ou B.

3-Leitura e Escrita: Oferece funções para ler e escrever dados em setores e blocos específicos de um cartão RFID.

4-Identificação de Cartões: A biblioteca permite verificar a presença de um cartão e ler seu UID (Identificador Único).

5-Halt (Parar) do Cartão: Permite desativar a comunicação com um cartão, tornando-o inativo.

6-Tipo de Cartão: Fornece informações sobre o tipo de cartão RFID detectado (por exemplo, MIFARE Classic, MIFARE Ultralight, etc.).

Essa biblioteca é amplamente utilizada em projetos que envolvem controle de acesso, sistemas de identificação, sistemas de pagamento, entre outros, que necessitam da tecnologia RFID para funcionar.

Aproxime o cartão RFID do leitor para iniciar o processo de leitura.
As informações do cartão, incluindo o UID e dados específicos, serão exibidas no LCD.
O sistema suporta leitura de dados de setores específicos do cartão MIFARE.
Configuração:

O código está configurado para funcionar com o módulo MFRC522 e um display LCD.
Certifique-se de conectar os pinos corretamente de acordo com as definições no código.
Personalize a chave de autenticação MIFARE conforme necessário.
Observações:

Este projeto é uma implementação básica e pode ser expandido para incluir mais funcionalidades, como armazenamento em banco de dados ou integração com serviços da IoT.

#include <SPI.h>
#include <MFRC522.h>
#include <LiquidCrystal.h>

#define SS_PIN 10
#define RST_PIN 9
MFRC522 mfrc522(SS_PIN, RST_PIN);

LiquidCrystal lcd(6, 7, 5, 4, 3, 2);

MFRC522::MIFARE_Key key;

void setup() {
  Serial.begin(9600);
  SPI.begin();
  mfrc522.PCD_Init();
  lcd.begin(16, 2);
  mensageminicial();
  for (byte i = 0; i < 6; i++) key.keyByte[i] = 0xFF;
}

void loop() {
  while (!mfrc522.PICC_IsNewCardPresent()) {
    delay(100);
  }
  
  if (mfrc522.PICC_ReadCardSerial()) {
    modo_leitura();
  }
}

void mensageminicial() {
  Serial.println("Aproxime o seu cartao do leitor...");
  lcd.clear();
  lcd.print("Aproxime o seu");
  lcd.setCursor(0, 1);
  lcd.print("cartao do leitor");
}

void modo_leitura() {
  Serial.print("UID da tag : ");
  String conteudo = "";
  byte letra;
  for (byte i = 0; i < mfrc522.uid.size; i++) {
    Serial.print(mfrc522.uid.uidByte[i] < 0x10 ? " 0" : " ");
    Serial.print(mfrc522.uid.uidByte[i], HEX);
    conteudo.concat(String(mfrc522.uid.uidByte[i]<0x10 ? " 0" : " "));
    conteudo.concat(String(mfrc522.uid.uidByte[i], HEX));
  }
  Serial.println();
  byte sector         = 1;
  byte blockAddr      = 4;
  byte trailerBlock   = 7;
  byte status;
  byte buffer[18];
  byte size = sizeof(buffer);
  status=mfrc522.PCD_Authenticate(MFRC522::PICC_CMD_MF_AUTH_KEY_A,
                                  trailerBlock, &key, &(mfrc522.uid));
  if (status != MFRC522::STATUS_OK) {
    Serial.print(F("PCD_Authenticate() failed: "));
    Serial.println(mfrc522.GetStatusCodeName(status));
    return;
  }
  status = mfrc522.MIFARE_Read(blockAddr, buffer, &size);
  if (status != MFRC522::STATUS_OK) {
    Serial.print(F("MIFARE_Read() failed: "));
    Serial.println(mfrc522.GetStatusCodeName(status));
  }
  lcd.clear();
  lcd.setCursor(0, 0);
  for (byte i = 1; i < 16; i++) {
    Serial.print(char(buffer[i]));
    lcd.write(char(buffer[i]));
  }
  Serial.println();
  sector         = 0;
  blockAddr      = 1;
  trailerBlock   = 3;
  status=mfrc522.PCD_Authenticate(MFRC522::PICC_CMD_MF_AUTH_KEY_A,
                                  trailerBlock, &key, &(mfrc522.uid));
  if (status != MFRC522::STATUS_OK) {
    Serial.print(F("PCD_Authenticate() failed: "));
    Serial.println(mfrc522.GetStatusCodeName(status));
    return;
  }
  status = mfrc522.MIFARE_Read(blockAddr, buffer, &size);
  if (status != MFRC522::STATUS_OK) {
    Serial.print(F("MIFARE_Read() failed: "));
    Serial.println(mfrc522.GetStatusCodeName(status));
  }
  lcd.setCursor(0, 1);
  for (byte i = 0; i < 16; i++) {
    Serial.print(char(buffer[i]));
    lcd.write(char(buffer[i]));
  }
  Serial.println();
  mfrc522.PICC_HaltA();
  mfrc522.PCD_StopCrypto1();
  delay(3000);
  mensageminicial();
}

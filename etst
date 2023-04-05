#include <Wire.h>  //libreria per la comunicazione I2C
#include <LiquidCrystal_I2C.h>  //libreria per il display LCD I2C
#define ADDR 0x38  //indirizzo I2C del display LCD I2C
#define MOISTURE_SENSOR A0  //pin analogico del sensore di umidità del suolo

LiquidCrystal_I2C lcd(ADDR, 2, 1, 0, 4, 5, 6, 7, 3, POSITIVE);  //inizializzazione del display LCD I2C

void setup() {
  lcd.begin(16,2);  //imposta il numero di colonne e righe del display
  lcd.backlight();  //accende la retroilluminazione del display
  lcd.setCursor(0,0);  //posiziona il cursore all'inizio della prima riga del display
  lcd.print("Umidita' del suolo");  //stampa il titolo sulla prima riga del display
  pinMode(MOISTURE_SENSOR, INPUT);  //imposta il pin del sensore di umidità del suolo come input
}

void loop() {
  int moisture = analogRead(MOISTURE_SENSOR);  //leggi il valore analogico del sensore di umidità del suolo
  int percent_moisture = map(moisture, 0, 1023, 0, 100);  //mappa il valore analogico in percentuale di umidità del suolo
  lcd.setCursor(0,1);  //posiziona il cursore all'inizio della seconda riga del display
  lcd.print("Umidita': ");  //stampa la descrizione dell'umidità del suolo sulla seconda riga del display
  lcd.print(percent_moisture);  //stampa il valore dell'umidità del suolo sulla seconda riga del display
  lcd.print("%");  //stampa il simbolo percentuale sulla seconda riga del display
  delay(500);  //attendi mezzo secondo
}

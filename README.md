# watchdog
Watchdog Test Neuer oder alter Bootloader?

/*
  Watchdog Test mit internerem Timer
  Nur mit neuem Bootloader richtig zu nutzen !
*/

#include <avr/wdt.h>
 
void setup() {
  //Die Dauer, bis der Watchdog auslösen soll
  //wdt_enable(WDTO_15MS);
  //wdt_enable(WDTO_30MS);
  //wdt_enable(WDTO_60MS);
  //wdt_enable(WDTO_120MS);
  //wdt_enable(WDTO_250MS);
  //wdt_enable(WDTO_500MS);
  //wdt_enable(WDTO_1S);
  //wdt_enable(WDTO_2S);
  //wdt_enable(WDTO_4S);
  //wdt_enable(WDTO_8S);

    pinMode(3, OUTPUT); // Test LED Reset
    pinMode(4, OUTPUT); // Test LED loop
    pinMode(5, INPUT);  // Reset Watchdog Eingang

 //--------- Reset LED ein - aus -ein - aus  
    digitalWrite(3, HIGH);
    delay(500);      
    digitalWrite(3, LOW);
    delay(500);      
    digitalWrite(3, HIGH);
    delay(500);      
    digitalWrite(3, LOW); 
    
// ---- Watchdog Befehle ---
    wdt_disable();        // WD ausschalten
    wdt_enable(WDTO_8S);  // WD einschalten 
    wdt_reset();          // WD zurücksetzen
}

void loop() {
    digitalWrite(4, HIGH);
    delay(500); // 0,5 Sekunden    
    digitalWrite(4, LOW);
    delay(500); // 0,5 Sekunden   

// ----- Reset Watchdog solange Eingang 5 = Low  
      if (digitalRead(5) == LOW) {wdt_reset();}
}

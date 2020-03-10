# watchdog
Watchdog Test Neuer oder alter Bootloader?

Watchdog Test mit internerem Timer
Nur mit neuem Bootloader richtig zu nutzen !

#include <avr/wdt.h>
 
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

---- Watchdog Befehle ---
    wdt_disable();        // WD ausschalten
    wdt_enable(WDTO_8S);  // WD einschalten 
    wdt_reset();          // WD zurücksetzen 

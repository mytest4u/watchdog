Watchdog Test mit internem Timer
Nur mit neuem Bootloader richtig zu nutzen !

Wer sicher gehen will dass seine Anwendung auf dauer störungsfrei läuft, kommt um die Funktion WD nicht herum.
Voraussetzung ist ein neuer Bootloader. Mit dem alten Bootloader hängt sich der Arduino im Bootmenü auf.

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

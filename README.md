---
# clignotant-warning-velo

Ce projet permet d'allumer un clignotant gauche/droite, ainsi qu'un clignotant "warning", avec simplement 3 boutons.
---
# vidéo du montage
[![video](https://img.youtube.com/vi/OF8e3JVgxyo.jpg)](https://www.youtube.com/watch?v=OF8e3JVgxyo)

---
# Montage

![SCHEMA](schema-clignotant-warning_bb.jpg)

---

# le code arduino

``` c++

#include <LedControl.h>

LedControl matrix(12,11,10,1);


void setup() {
  // 

  
 Serial.begin(9600);
 
 pinMode(7,INPUT);
 pinMode(4,INPUT);
 pinMode(2,INPUT);


 matrix.shutdown(0, false);
 

}

void loop() {
  // 

  int buttonLeft = digitalRead(7);
  int buttonRight = digitalRead(4);
  int buttonWarning = digitalRead(2);
  
  Serial.println(buttonLeft);
  

  matrix.clearDisplay(0);
  
  if(buttonLeft == 1) { 
    
    matrix.setLed(0, 0, 3, true);
    matrix.setLed(0, 1, 2, true);
    matrix.setLed(0, 1, 3, true);
    matrix.setLed(0, 2, 1, true);
    matrix.setLed(0, 2, 2, true);
    matrix.setLed(0, 2, 3, true);
    matrix.setLed(0, 3, 0, true);
    matrix.setLed(0, 3, 1, true);
    matrix.setLed(0, 3, 2, true);
    matrix.setLed(0, 3, 3, true);
    matrix.setLed(0, 3, 4, true);
    matrix.setLed(0, 3, 5, true);
    matrix.setLed(0, 3, 6, true);
    matrix.setLed(0, 4, 0, true);
    matrix.setLed(0, 4, 1, true);
    matrix.setLed(0, 4, 2, true);
    matrix.setLed(0, 4, 3, true);
    matrix.setLed(0, 4, 4, true);
    matrix.setLed(0, 4, 5, true);
    matrix.setLed(0, 4, 6, true);
    matrix.setLed(0, 5, 1, true);
    matrix.setLed(0, 5, 2, true);
    matrix.setLed(0, 5, 3, true);
    matrix.setLed(0, 6, 2, true);
    matrix.setLed(0, 6, 3, true);
    matrix.setLed(0, 7, 3, true);

    delay(500);

    matrix.clearDisplay(0);
    

    delay(500);
}

 if(buttonRight == 1) { 
    
    matrix.setLed(0, 0, 3, true);
    matrix.setLed(0, 1, 3, true);
    matrix.setLed(0, 1, 4, true);
    matrix.setLed(0, 2, 3, true);
    matrix.setLed(0, 2, 4, true);
    matrix.setLed(0, 2, 5, true);
    matrix.setLed(0, 3, 0, true);
    matrix.setLed(0, 3, 1, true);
    matrix.setLed(0, 3, 2, true);
    matrix.setLed(0, 3, 3, true);
    matrix.setLed(0, 3, 4, true);
    matrix.setLed(0, 3, 5, true);
    matrix.setLed(0, 3, 6, true); 
    matrix.setLed(0, 4, 0, true);
    matrix.setLed(0, 4, 1, true);
    matrix.setLed(0, 4, 2, true);
    matrix.setLed(0, 4, 3, true);
    matrix.setLed(0, 4, 4, true);
    matrix.setLed(0, 4, 5, true);
    matrix.setLed(0, 4, 6, true);   
    matrix.setLed(0, 5, 3, true);
    matrix.setLed(0, 5, 4, true);
    matrix.setLed(0, 5, 5, true);
    matrix.setLed(0, 6, 3, true);
    matrix.setLed(0, 6, 4, true);
    matrix.setLed(0, 7, 3, true);

    delay(500);

    matrix.clearDisplay(0);
    

    delay(500);
   
}

   if(buttonWarning == 1) { 
    
    matrix.setLed(0, 1, 3, true);
    matrix.setLed(0, 1, 4, true);
    matrix.setLed(0, 2, 3, true);
    matrix.setLed(0, 2, 4, true);
    matrix.setLed(0, 3, 3, true);
    matrix.setLed(0, 3, 4, true);
    matrix.setLed(0, 4, 3, true);
    matrix.setLed(0, 4, 4, true);
    matrix.setLed(0, 5, 3, true);
    matrix.setLed(0, 5, 4, true);    
   
    matrix.setLed(0, 7, 3, true);
    matrix.setLed(0, 7, 4, true);

    delay(1000);

    matrix.clearDisplay(0);
    

    delay(500);
   
}  
}
```
---

# Bibliothéques

``` c++
#include <LedControl.h>

LedControl matrix(12,11,10,1);
```
---

# Liste des composants

[planche à pain](https://www.amazon.fr/Hilitand-Planche-Prototype-Soudure-Plastique/dp/B07GZJBDCP/ref=sr_1_3?s=computers&ie=UTF8&qid=1548257336&sr=1-3&keywords=planche+pain)

[matrice](https://www.amazon.fr/Matrice-transparente-cascade-Arduino-MAX7219/dp/B00GKEMQUM/ref=asc_df_B00GKEMQUM/?tag=googshopfr-21&linkCode=df0&hvadid=48657591686&hvpos=1o2&hvnetw=g&hvrand=6322799427567728259&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9056525&hvtargid=pla-83304435926&psc=1)

[résistance 220 W](https://www.amazon.fr/POPESQ%C2%AE-Resistance-Utilisable-Aussi-A2456/dp/B07L2MKDYN/ref=sr_1_1?s=electronics&ie=UTF8&qid=1548258125&sr=1-1&keywords=r%C3%A9sistance+220+ohms+arduino)

[bouton poussoir](https://www.amazon.fr/panneau-momentan%C3%A9-poussoir-interrupteur-broches/dp/B00841ZQXS/ref=asc_df_B00841ZQXS/?tag=googshopfr-21&linkCode=df0&hvadid=227982899234&hvpos=1o2&hvnetw=g&hvrand=11730873474171896983&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9056525&hvtargid=pla-434613410574&psc=1)

# micro:bit workshop pre učiteľov

## 1. Úvod

### Python
Python je veľmi populárny a všestranný programovací jazyk odporúčaný pre vyučovanie základov programovania. Práve preto postupne nahrádza iné programovacie jazyky na hodinách informatiky. Vo veľkom Python využívajú aj v Google, Dropbox, Európskej organizácii jadrového výskumu CERN, sociálnych sieťach Facebook, Pinterest a Instagram, či pri vyučovaní na prestížnej vysokej škole MIT.

Autorom jazyka Python je Guido van Rossum (prvá verzia je z 1989). V súčasnosti jazyk Python vyvíja a spravuje komunita, zastrešovaná medzinárodnou organizáciou Python Software Foundation (skratka PSF). Samotný jazyk je open-source.

Python je interpretovaný jazyk, a preto sa po dopísaní kódu ho neskompilujeme (ako napríklad C či Pascal) ale spustíme ho v interpreteri. Ten náš kód za chodu číta a prekladá na strojové inštukcie pre procesor. Preto je potrebné, aby sme na spustenie Python kódu mali na počítači nainštalovaný Python interpreter. (ako si vysvetlíme o schvíľu)

Odporúčame používať najnovšiu verziu Python3 (v súčasnosti je to Python3.6). Python2 je staršia verzia Pythonu a už nie je vhodné v nej programovať.

V čom sa Python líši snáď najviac od iných programovacích jazykov je práve komunika. Tá je tvorená profesionálmi, začiatočníkmi, učiteľmi i víkendovými programátormi a tak je veľmi rôznorodá. Po celom svete sa pravidelne organizujú konferencie PyCon (čiže PYthon CONference). Na Slovensku je táto konferencia organizovaná raz ročne občianskym združením SPy (Slovak Python User Group).

### MicroPython
MicroPython je upravená verzia Pythonu, ktorá beží aj na menej výkonných zariadeniach. Vďaka tomu vieme v MicroPythone programovať mikroelektroniku a interagovať s okolitým svetom pomocou LED diód, senzorov, bzučiakov, motorčekov, atď. Takéto zariadenia sú zároveň rádovo lacnejšie ako počítače pre klasický Python. Obrovskou výhodou je fakt, že syntax je pre obe verzie jazyka rovnaká, a tak sa učiteľom aj žiakom stačí naučiť iba jeden jazyk.

Tak ako na spustenie Python kódu na počítači potrebuje nainštalovaný interpreter, tak aj pre MicroPython kód musíme na mikroprocesom najprv nainsťalovať MicroPython interpreter. To stačí spraviť raz a následne mu budeme už len posielať naše zdrojové kódy na preklad. Raz za čas sa ale oplatí MicroPython na zariadení preinštalovať na novšiu verziu, aby sme mali vždy čo najviac funkčný interpreter.

MicroPython interpreter vymyslel Damien George v roku 2013 pre vývojovú dosku pyboard (s mikroprocesorom STM32). V súčasnosti existuje viacero verzií MicoPythonu pre rôzne mikroprocesory. My budeme používať verziu pre micro:bit.

### Čo je to micro:bit?
Malá edukačná doska vhodná pre využitie vrámci hodín informatiky na základných a stredných školách. Vďaka konektorom (tzv. pinom) je možné ňou programovať hardvér.

### Ako môžem micro:bit progtamovať?
Je možné programovať ho v MicroPythone, C, JavaScripte a cez Blockly (podobné Scratch). 

### Blokové programovanie (Blockly)
[Online Blockly Editor (SK)](https://makecode.microbit.org/?lang=sk_SK) je online editor pre programovanie micro:bitu cez grafický programovac jazyk. Pri tomto spôsobe programovania nie je potrebná inštalácia softvéru na počítač či administrátorské práva, stač prístup na internet a internetový prehliadač.

#### Základné
Zobraziť reťazec - vypíše text na obrazovke

Zobrazi LED - zobrazí obrázok na obrazovke
#### Vstup
V tejto časti sa nachádzajú bloky, ktoré spostia kód pri nejakej situácii - napríklad pri stlačení tlačidla, naklonen dosky alebo zatrasení.
#### Hudba
Microbit dokáže generovať aj zvuk, a to konkrétne na kolíku 0. Preto k nemu pripojíme jeden káblik mikrofónu (dátový) a druhý (zem) pripojíme k ``GND``. Skúste si spustiť melódio _svadba_. 
#### Radio
Micro:bit obsahuje aj vbudovaný komunikačný modul, a teda vedia medzi sebou navzájom komunikovať.
#### Cykly, Logiku, Premenné, Matematika
Tak ako v Scratch, aj Blockly obsahuje základné programátorské bloky. Zajímavým môže byť _vybrať náhodne od 0 po n_, ktor generuje náhodné čísla.

### Online MicroPython Editor
[Online MicroPython Editor (EN)](http://python.microbit.org/) je ďaľší online editor, no tento krát je urený pre tvorby MicroPython kódu. Ani pri tomto spôsobe programovania nie je potrebná inštalácia softvéru na počítač či administrátorské práva, stač prístup na internet a internetový prehliadač.

#### Hello World!
```python
from microbit import *

while True:
    display.scroll('Hello, World!')
    display.show(Image.HEART)
    sleep(2000)
```
* __from micobit import \*__ - tento príkaz nám v kóde sprístupní všetku funkcionalitu knižnice microbit, vďaka ktorej vieme pristupova k hardérovej funkcionalite micro:bitu.
* __while True:__ - tento príkaz nám bude donekonečna vykonávať kód, ktorý prislúcha do daného wile cyklu
* __Indentácia__ . v Pythone (na rozdiel od iných jazykov) sa kód prislúchajúci do bloku neoznačuje zátvorkami, ale pomocou odsadzovania, čiže indentácie. Aby nejaký kód prislúchal pod príkaz _while_, musí byť odsadený aspoň o jeden tabulátor (štyri medzerníky)
* __display.scroll()__ vypíše daný reťazec na obrazovku
* __display.show(Image.HEART)__ vykreslí daný obrázok na obrazovku
* __sleep()__ - funkcia sleep pozastaví micro:bit na zadaný počet milisekúnd
* __poznámky__ - poznámky sa v Pythone tvoria mriežkou (#)

Ako ale zislíme, aké možné obrázky môžeme vykresliť? Na to nám slúži [online micro:bit MicroPython dokumentácia](http://microbit-micropython.readthedocs.io/en/latest/tutorials/images.html), v ktorej je zoznam všetkých príkazov, ktor je možné použiť.

### Mu Editor
[Mu (čoskoro v SK)](https://codewith.mu/) je IDE pre písanie MicroPython kódu pre micro:bit, ako aj pre Python3 (skvelá alternatíva k IDLE). Je možné ho stiahnu a spustiť bez inštalácie, alebo inštalovať pomocou nástroja ``pip``. Pre plnú funkcionalitu je potrebné pri platforme Windows stiahnúť si driver pre micro:bit.

### Zvuk (Music & Speech)
#### Pregprogramovaná hudba

```python
import music

music.play(music.NYAN)
```

* __music__ - kinižnica na generovanie hudby na _pine 0_
* __music.NYAN__ - micro:bit už má niekoľko predprogramovaných melódií, tie nájdete v dokumnetácii (sekcia Music)

#### Vlastná hudba
```python
import music

tune = ["C4:4", "D", "E", "C", "C", "D", "E", "C", "E", "F", "G:8",
        "E:4", "F", "G:8"]
music.play(tune)
```
* __C4:4__ - nota C zo štvrtej oktávy s dĺžkou 4

#### Zvukové efekty
```python
import music

while True:
    for freq in range(880, 1760, 16):
        music.pitch(freq, 6)
    for freq in range(1760, 880, -16):
        music.pitch(freq, 6)
```

### NeoPixel
```python
from microbit import *
import neopixel

np = neopixel.NeoPixel(pin1, 8)
np[0] = (255, 0, 0)
np.show()

```

```python
from microbit import *
import neopixel

np = neopixel.NeoPixel(pin1, 8)
np[0] = (255, 0, 0)
np[1] = (255, 0, 0)
np[2] = (255, 0, 0)
np[3] = (255, 0, 0)
np[4] = (255, 0, 0)
np[5] = (255, 0, 0)
np[6] = (255, 0, 0)
np[7] = (255, 0, 0)
np.show()

```

```python
from microbit import *
import neopixel

np = neopixel.NeoPixel(pin1, 8)

for i in range(0, 8)
    np[i] = (255, 0, 0)
np.show()

```


```python
from microbit import *
import neopixel
from random import randint, seed

seed(5)
np = neopixel.NeoPixel(pin1, 8)

while True:

    for i in range(0, len(np)):
        red = randint(0, 255)
        green = randint(0, 255)
        blue = randint(0, 255)

        np[i] = (red, green, blue)

        np.show()
        sleep(500)
```

```python
from microbit import *
import neopixel

np = neopixel.NeoPixel(pin1, 8)

while True:

    for i in range(0, len(np)):
        for led_id in range(0, len(np)):
            if i == led_id:
                np[led_id] = (0, 255, 0)
            else:
                np[led_id] = (0, 0, 0)
        sleep(100)
        np.show()
```

```python
from microbit import *
import neopixel

np = neopixel.NeoPixel(pin1, 8)   # Vytvor NeoPixel driver pre 8 pixelov

while True:
    # bounce
    for i in range(len(np)):
        for led_id in range(len(np)):
            if i == led_id:
                np[led_id] = (0, 255, 0)
            else:
                np[led_id] = (0, 0, 0)
        sleep(100)
        np.show()

    # fade in
    for i in range(0, 256, 1):
        for led_id in range(len(np)):
            np[led_id] = (0, i, 0)
        np.show()

    # fade out
    for i in range(255, 0, -1):
        for led_id in range(len(np)):
            np[led_id] = (0, i, 0)
        np.show()

    # clear
    for i in range(len(np)):
        np[i] = (0, 0, 0)
    np.show()
```

### Vstup na kolíky
```python
from microbit import *

while True:
    if pin2.read_digital():
        display.show(Image.HAPPY)
    else:
        display.show(Image.SAD)
```

Teraz zameň ``read_digital`` za ``is_touched``.
Namiesto kábliku použi na prepojenie kúsky alobalu a ruky.
Vyskúšaj to aj cez Banán, Jablko či pomaranč.

### Banánové piano
```python
from microbit import *
import music

tune = ["C4:4", "D", "E", "C", "C", "D", "E", "C", "E", "F", "G:8",
        "E:4", "F", "G:8"]
i = 0

while True:
    if pin2.is_touched():
        music.play(tune[i])
        i += 1
        if i == len(tune):
            i = 0
```
Toto naše piano vieme rozšíriť ešte aj o svetlo - pri každom stlačení klávesu náhodne zmeníme všetky farby na LED pásiku.

### Hra na reflexy
TBA

### Diaľkový vypínač
```python
import radio
from microbit import *

radio.on()

while True:
    if button_a.was_pressed():
        radio.send('on')
    elif button_b.was_pressed():
        radio.send('off')
```
```python
import radio
from microbit import *

radio.on()

while True:
    incoming = radio.receive()
    if incoming == 'on':
        display.show(Image.HAPPY)
    elif incoming == 'off':
        display.show(Image.SAD)
```
```python
import radio
from microbit import *
import music

radio.on()

while True:
    incoming = radio.receive()
    if incoming == 'on':
        display.show(Image.HAPPY)
        music.play(music.JUMP_UP)
    elif incoming == 'off':
        display.show(Image.SAD)
        music.play(music.JUMP_DOWN)
```

### Wireless Sniffer
```python
import radio
from microbit import *

radio.on()

while True:
    incoming = radio.receive()
    if incoming:
        print(incoming)
```
### Robot buggy

### To mention:
* Relay, Humidity sensors, PIR sensors, Rain sensor
* Robotics
* 



### Odkazy a inšpirácia
* [Online micro:bit MicroPython dokumentácia (EN)](http://microbit-micropython.readthedocs.io)
* [Štatistika z Veľkej Británie (EN)](http://microbit.org/en/2017-07-07-bbc-stats/)
* [microbit.org/ideas/projects (EN)](http://microbit.org/ideas/projects/)
* [microbit.hackster.io (EN)](https://microbit.hackster.io/)
* [BBC článok s micro:bit projektami (EN)](http://www.bbc.com/news/technology-35824446)
* [micro:bit projekty na itpro.co.uk (EN)](http://www.itpro.co.uk/desktop-hardware/26289/13-top-bbc-micro-bit-projects)

## Kde kúpiť micro:bit
* [rlx.sk (SK)](https://rlx.sk/sk/accessories-ipod/5676-microbit-board-sf-dev-14208-bbc-microbit-af-3530-640522711048.html)
* [Kitronics (EN)](https://www.kitronik.co.uk/5615-bbc-microbit-starter-kit.html)
* [Piromoni (EN)](https://shop.pimoroni.com/products/microbit)
* [Farnell/Element14 (EN)]()



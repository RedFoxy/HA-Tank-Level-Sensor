
# Tank Level - EN
Sensor for the water, pellets or other, level inside a tank, the project is based on an ESP8266 / Wemod D1 Mini and an ultrasonic sensor like HC-SR04 or the waterproof version JSN-SR04T, recommended in humid environments, you can also use other compatible ultrasonic sensors, the project includes 8 LEDs to physically show how full the tank is even without using the web interface or Home Assistant, the ESP8266 is programmed using ESPHome.

## What you need:
- Wemod D1 Mini or other ESP8266 board
- Ultrasonic sensor like HC-SR04 or JSN-SR04T
- Power state 220v - 5v
- 3 red leds (optional)
- 2 yellow leds  (optional)
- 2 green leds (optional)
- 7 resistors 220 ohm (optional)

## Dependences
- ESPHome https://esphome.io/

## Wire connections
![Schema del sensore](/doc/image/tank_sensor_scheme.jpg)

## Board programming
**WIP in english**
[tank-level-sensor.yaml](/tank-level-sensor.yaml)

## Show Tank status
![Home Assistant - Water Tank example](/doc/image/ha-example.jpg)

**WIP in english**

[dashboard-card-gauge.yaml](/dashboard-card.yaml) dependences [Bar card](https://github.com/custom-cards/bar-card) and [Lovelace Card mod](https://github.com/thomasloven/lovelace-card-mod).
[dashboard-card-gauge.yaml](/dashboard-card-gauge.yaml), una semplice card con gauge nella 

## Extra files
**WIP in english**

# Tank Level - IT
Sensore per il livello dell'acqua, pellet o altro, dentro una cisterna, il progetto è basato su un ESP8266/Wemod D1 Mini e un sensore a ultrasuoni HC-SR04 o la versione impermeabile JSN-SR04T, consigliata in ambienti umidi, potete usare anche altri sensori a ultrasuoni compatibili, nel progetto è prevista la presenza di 8 led per mostrare fisicamente quanto sia piena la cisterna anche senza usare l'interfaccia web o Home Assistant, l'ESP8266 è programmato usando ESPHome.

## Materiali necessari:
- Wemod D1 Mini o altra board basata su ESP8266
- Sensore a ultrasuoni come HC-SR04 o JSN-SR04T
- Modulo di alimentazione 220v - 5v
- 3 led rossi (opzionali)
- 2 led gialli (opzionali)
- 2 led verdi (opzionali)
- 7 resistenze da 220 ohm (opzionali)

## Dipendenze
- ESPHome https://esphome.io/

## Schema connessioni
![Schema del sensore](/doc/image/tank_sensor_scheme.jpg)

## Programmazione della board
Nota bene: Prima di procedere, effettuate tutti i collegamenti mostrati nello schema, si consiglia di usare una board Wemos D1 Mini, in caso contrario dovrete personalizzare il codice in modo da assegnare le corrette porte GPIO.

Collegate il Wemos D1 Mini, o altra board basata su ESP8266, al computer, verificate che venga configurato correttamente come porta seriale, in caso installate i driver della vostra versione.
Aprite l'interfaccia di ESPHome, se non avete ancora installato ESPHome, potete installarlo come plugin di Home Assistant o in modo indipendente, come specificato sul sito https://esphome.io/ alle voci **Get Started**.
Create un nuovo progetto in ESPHome, seguite la guida per collegarvi alla vostra board.
Editate il codice del progetto appena creato, sostituendolo con quello presente nel file [tank-level-sensor.yaml](/tank-level-sensor.yaml).
Personalizzate il codice inserendo i dati della vostra cisterna e della vostra connessione.
**--ATTENZIONE!--**
- Le configurazioni riportanti la dicitura **!secret** vengono lette dal file secret di ESPHome, in caso potete personalizzarle a mano o inserire nel file secret con gli stessi nomi di variabile.
- Lo script è pensato per usare un ip statico, se volete usare il DHCP dovete rimuovere il blocco manual_ip e le relative sottovoci

Dopo aver personalizzato il codice, salvate e inviate (install) il programma alla vostra board.
Se è andato a buon fine, dopo poco vedrete il log da parte dell'ESP8266 con le informazioni sulla distanza dal sensore, il volume e la percentuale di quanto la cisterna sia piena.

## Mostrare lo stato della cisterna
![Home Assistant - Water Tank example](/doc/image/ha-example.jpg)
Potete mostrare lo stato della cisterna con qualsiasi grafica vogliate, potete usare il valore del volume in litri o la percentuale, come più vi aggrada, nel progetto ho allegato due possibili card per mostrare lo stato della cisterna, il primo [dashboard-card-gauge.yaml](/dashboard-card.yaml) mostra una barra che si riempe e cambia colore in base a quanto è piena la cisterna, quando la cisterna si riempe o si svuota viene mostrato anche un triangolino con la punta in su o in giù, questa card necessita di due plugin per funzionare correttamente [Bar card](https://github.com/custom-cards/bar-card) e [Lovelace Card mod](https://github.com/thomasloven/lovelace-card-mod), il secondo esempio è [dashboard-card-gauge.yaml](/dashboard-card-gauge.yaml), una semplice card con gauge nella quale ho impostato i vari limiti.

## File aggiuntivi
Nella cartella Doc potete trovare sia lo schema che un PCB pronto per essere stampat, il tutto realizzato usando Fritzing, inoltre allego le foto del sensore che ho realizzato per il mio serbatoio dell'acqua, anche se ci sono più led per un errore di calcolo, per il resto rende l'idea del progetto finito.

Fatemi sapere se gradite il progetto!

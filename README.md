# Projektseite "Smooosh"
von Tim Wähner und David Rettmann                                                                   
Stormarnschule Ahrensburg                                                                                             
Klasse 12e                                                                                                       
Schuljahr 18/19                                                                                                       


## Inhalt

[1. Vorwort](#1)                   
[2. Beschreibung](#2)  
[3. Erläuterung](#3)  
[4. Herausforderungen](#4)                                                                                              
[5. Schlusswort](#5)

## Vorwort<a name="1"></a>

"Smooosh" ist ein Spiel, das im Rahmen des Informatikunterrichts in der 12. Klasse von uns in Gamelab auf code.org programmiert wurde. Wir sind ohne jegliche Erfahrungen im Programmieren in dieses Projekt hineingegangen. Gamelab bot uns in dieser Hinsicht eine gute Plattform, da es eine Blockprogrammiersprache ist und wir dort erste Erfahrungen sammeln und die Anfänge des Programmieren lernen konnten.                                                                                                                  
Das Grundprinzip des Spiels "Smooosh" ist angelehnt an das Spiel "Super Smash Bros.". Es geht darum den Gegenspieler von der Spielfläche herunterzukicken. Unseres unterscheidet sich jedoch in einigen Aspekten erheblich vom Original.                                   
Auf dieser Seite werden wir das Spiel zunächst [beschreiben](#2) und daraufhin die Umsetzung der einzelnen Aspekte näher [erläutern](#3).


## Beschreibung<a name="2"></a>

Startet man unser Spiel, gelangt man zunächst in ein [Startmenü](#Menüs). Um Fortzufahren muss man nun "space" drücken. Damit gelangt man in das [Spielermenü](#Menüs) 1, in dem sich Spieler 1 einen Charakter aussuchen kann, den er spielen möchte. Die Charaktere unterscheiden sich lediglich im Aussehen, aber nicht in den Fähigkeiten. Nachdem er Einen per Mausklick ausgewählt hat, steht Spieler 2 im [Spielermenü](#Menüs) 2 vor der gleichen Entscheidung. Neben den Charakteren wird der Spieler auch mit der Steuerung vertraut gemacht. Haben beide einen Charakter ausgewählt, startet das Spiel.                     
                                                                                                                                       
Die [Steuerung](#Steuerung) für Spieler 1 liegt auf den Tasten "W" für den Sprung, "A" für eine Bewegung nach links, "D" für eine Bewegung nach rechts und "S" für einen noch schnelleren Fall. Für Spieler 2 liegt die Steuerung in der gleichen Formation auf den Pfeiltasten "up", "left", "right" und "down".          
                                                                                                                                      
Im Spiel herrscht eine generelle Beschleunigung nach unten, sprich eine ["Gravitation"](#Gravitation). Die Tasten "S" für Spieler 1 und "down" für Spieler 2 geben dem Charakter einen extra Schub, sodass sie noch schneller fallen.                                          
                                                                                                                                    
Neben den beiden Spielern existieren auf dem ["Spielfeld"](#Spielfeld) eine Sonne in der oberen linken Ecke ohne weitere Funktionen und drei Wolken vor einem hellblauen Hintergrund, die in festgelegten Bereichen an zufälligen Orten erscheinen und die Plattformen bilden, auf denen sich die Charaktere bewegen können. Zwei von ihnen bewegen sich ständig hin und her, eine vertikal und eine horizontal. Die Charaktere der Spieler spawnen jeweils auf einer dieser Plattformen.                                                                 
                                                                                                                                        
Um sich gegenseitig nun von den Plattformen herunterzubekommen, gibt es mehrere Möglichkeiten: Zum einen können die Spieler den [Sprung](#Sprung), oder den Doppelsprung nutzen, um an ihren Gegner heranzukommen und diesen mithilfe des Charakters [herunterzuschubsen](#Schubserei). Zum anderen verfügen beide Spieler über die Möglichkeit den Gegner mit einem [Geschoss](#Geschoss) herunterzuschieben. Für Spieler 1 liegt das Geschoss auf den Tasten ["Q"](#Geschoss), um nach links und ["E"](#Geschoss), um nach rechts zu schießen. Bei Spieler 2 liegt es auf ["Alt"](#Geschoss) für links und ["Shift"](#Geschoss) für rechts. Neben dieser Eigenschaft, die jeder inne hat, gibt es auch [Powerups](#Powerup). Diese werden von einem in regelmäßigen Abständen quer durch das Spielfeld fliegenden Flugzeug abgeworfen und wenn man diese aufsammelt, beeinflusst man entweder sich selber positiv oder den Gegner negativ. Bei diesen Powerups gibt es drei Kategorien. Die erste beeinflusst den Sprung: Sammelt man das [roter Blitz Powerup](#RedBolt) ein, so kann der Gegner für eine kurze Zeit nicht springen und sammelt man das [grüner Blitz Powerup](#GreenBolt) ein, so kann man selber für einen kurzen Zeitraum unendlich oft hochspringen und ist nicht an den Doppelsprung gebunden. Mit den Powerups der zweiten Kategorie wird das Geschoss beeinflusst. Das [roter Schild Powerup](#RedShield) lässt den Gegner für kurze Zeit nicht schießen und das [grüner Schild Powerup](#GreenShield) lässt einen selber unendlich oft schießen und die Projektile bewegen sich schneller für eine kurze Zeit. Die letzte Kategorie verändert die Größe der Charaktere. Das [grüner Stern Powerup](#GreenStar) lässt einen selber wachsen und das [roter Stern Powerup](#RedStar) lässt den Gegner schrumpfen.                                                                                    
                                                                                                                                     
Schafft es nun einer der Spieler, den anderen von einer Plattform herunterzuschieben, sodass er es nicht schafft sich durch einen Sprung zu retten, verschwindet er sobald er das Spielfeld nach unten verlässt. Dies ist im Spiel der [Tod](#Tod). Zur Seite oder nach oben kann das Spielfeld nicht verlassen werden. Auf dem Bildschirm erscheint die Nachricht "Player [1/2] died" und der andere Spieler bekommt auf dem [Scoreboard](#Scoreboard) in der oberen rechten Ecke einen Punkt. Nach einer kurzen Zeit spawnen beide Charaktere wieder auf ihren [Spawnplätzen](#Tod) und sie können erneut versuchen sich gegenseitig herunterzuschubsen. Möchte man das Scoreboard zurücksetzen, kann man dies mit der Taste ["0"](#Scoreboard) tun. Möchte ein Spieler einen anderen Charakter spielen, kann man mit ["space"](#Steuerung) wieder in die Charakterauswahl gelangen.


## Erläuterung<a name="3"></a>

### Die Menüs<a name="Menüs"></a>

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/startmen%C3%BC.jpg" alt="image" width="500">

Im Startmenü haben wir versucht das Spiel so gut es geht generell wiederzuspiegeln. Die ähnliche Hintergrundfarbe und die Unterbringung der drei Charaktere und der Wolke als Plattform soll die direkte Verbindung zum Spiel darstellen. Erstellt haben wir das Startmenü extern auf dem Ipad mit Notability, um es im Programm als Sprite nutzen zu können. 

```
var start = createSprite(200, 200);
start.scale = 1.12;
start.visible = true;
start.setAnimation("Start");
```
Mit den beiden Spielermenüs haben wir es sehr ähnlich gehandhabt. Auch diese haben wir erst am Ipad erstellt und später als Sprite ins Programm hinzugefügt. 

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/Spieler%201%20auswahl.jpg" alt="image" width="500">

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/Spieler%202%20auswahl.jpg" alt="image" width="500">

Die Animationen der Charaktere haben wir schlussendlich vor die Sprites der Spielermenüs gesetzt und als Buttons programmiert um die Charaktere mit einem Mausklick auswählen zu können. Beispielsweise folgt der Code für Spieler 1 ("nini").

```
 if (player1.visible===true) {
    if (mousePressedOver(playerselect11)) {
      nini.setAnimation("elk");
    }
    if (mousePressedOver(playerselect12)) {
      nini.setAnimation("cow_1");
    }
    if (mousePressedOver(playerselect13)) {
      nini.setAnimation("elephant_happy_1");
    }
    drawSprites();
```


### Die Steuerung<a name="Steuerung"></a>

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/TAstatur%20endg%C3%BCltig.jpg" alt="image" width="1500">

Die Hauptsteuerungselemente auf die ich in diesem Teil eingehe sind die Steuerung der Charaktere und die Rückkehr in das Spielermenü. 
Die Steuerung der Charaktere basiert auf den Pfeiltasten und "wasd". Alle anderen Steuerungselemente werden im weiteren Verlauf der Erläuterung eingehend behandelt. 
                                                                                                     
Für den Spieler 2 liegt der Sprung auf "up":
```
if (keyWentDown("up")) {
    elk.velocityY = -15;
```
Die Bewegung nach links liegt auf "left":
```
if (keyDown("left")) {
   elk.x = elk.x-5;
```
Die Bewegung nach rechts liegt auf "right":
```
if ((keyDown("right"))) {
   elk.x = elk.x+5;
```
Der Schub nach unten liegt auf "down":
```
if (keyDown("down")) {
   elk.velocityY = elk.velocityY+10;
```

Für den Spieler 1 liegt der Sprung auf "w":
``` 
if (keyWentDown("w")) {
   nini.velocityY = -15;
```
Die Bewegung nach links liegt auf "A":                                                                            
```
if (keyDown("a")) {
    nini.x = nini.x-5;   
```
Die Bewegung nach rechts liegt auf "D":                                                                                      
```
if ((keyDown("d"))) {
    nini.x = nini.x+5;   
```
Der Schub nach unten liegt auf "S":                                                                                                
```
if (keyDown("s")) {
    nini.velocityY = nini.velocityY + 10;    
```

Wenn ein Spieler sich wünscht einen anderen Charakter zu spielen, so kann er dies mit "space" tun. Der Code dafür sieht wie folgt aus:
```
 if (keyDown ("space")) {
    start.visible = false;
    player1.visible = true;
    player2.visible = false;
  elk.visible = false;
  nini.visible = false;
  sun.visible = false;
  ground3.visible = false;
  ground2.visible = false;
  ground.visible = false;
  start1.visible = false;
  start2.visible = false;
  elk.x = start2.x;
  elk.y = start2.y-5;
  nini.x = start1.x;
  nini.y = start1.y-5;
  }
  drawSprites();
```

Zunächst wird die Startseite auf unsichtbar gestellt, weil das Programm nicht weiß ob du zum ersten Mal ins Spielermenü kommst oder nur wieder zurückkehrst. Daraufhin wird das Spielermenü 1 sichtbar gemacht und alle anderen Sprites unsichtbar. Die beiden Charaktere werden vorsorglich im Hintergrund bereits auf ihre Startspawnplattformen gestellt, sodass sie nach Verlassen des zweiten Spielermenüs nur sichtbar gemacht werden müssen. 


### Die Gravitation<a name="Gravitation"></a>

Die Gravitation haben wir im Code für den Schub nach unten als "Gegenstück" genutzt. Solange "S" oder "Down" nicht gedrückt werden, gilt eine ständige Beschleunigung nach unten. 

```
if (keyDown("down")) {
      elk.velocityY = elk.velocityY+10;
    } else {
      elk.velocityY = elk.velocityY + 1;
```

Anhand dieses Stück des Codes sieht man, dass wenn die Taste "Down" gedrückt wird eine Beschleunigung von 10 wirkt und sonst immer eine von 1.


### Das Spielfeld<a name="Spielfeld"></a>

Das Spielfeld ist an allen vier Seiten durch Edges begrenzt. Dies geht mit dem knappen, aber effektivem Command "createEdgeSprites();". Später muss noch für jeden Sprite ergänzt werden, dass er mit den Edges auch kollidiert.

```
elk.collide(edges);
nini.collide(edges);
```

Nun, da die Grenzen des Spielfelds klar sind, geht es als nächstes um die Optik des Spielfelds. Der Hintergrund ist einfach als hellblau durch den RGB (0, 192, 255) festgelegt.

```
function draw() {
  background(rgb(0, 192, 255));
```

Zuerst hatten wir den Hintergrund einfach als blaue Sprite, jedoch hat uns das vor weitgehende Probleme mit den Texten gestellt, deswegen haben wir uns umentschieden und den Hintergrund selber als hellblau festgelegt. 
In unserem stellt das hellblau den Himmel dar, deswegen ist es auch logisch, das es eine Sonne gibt. Diese befindet sich als Sprite in der oberen linken Ecke.

```
//sun
var sun = createSprite(69, 69);
sun.setAnimation("Sun_1");
sun.scale = 0.4;
```

Um das Himmelsthema weiter fortzuführen, sind die Sprites, die die Plattformen darstellen, Animationen von Wolken.

```
//ground1
var ground = createSprite(randomNumber(120, 130), 350);
ground.setAnimation("Wolke");
ground.height = 50;
ground.width = 120;
//ground2
var ground2 = (createSprite(randomNumber(100, 200), 200));
ground2.setAnimation("Wolke");
ground2.scale = 0.3;
//ground3
var ground3 = createSprite(ground.x+170, ground.y-randomNumber(30,70));
ground3.setAnimation("Wolke");
ground3.height = 30;
ground3.width = 100;
```

Wie im Code auch unschwer zu erkennen ist, erscheinen die Plattformen jedes Mal ein wenig unterschiedlich, durch die randomNumber in den Koordinaten. Neben dem zufälligen Erscheinungsort bewegen sich auch zwei der drei Plattformen. 

```
   ground2.velocityX = -0.5;
    ground3.velocityY = -0.5;
  }
  if ((ground2.x==50 && ground2.velocityX < 0)) {
    ground2.velocityX = 0.5;
  }
  if ((ground3.y)<=200 && ground3.velocityY < 0) {
    ground3.velocityY = 0.5;
  }
  if ((ground2.x==200 && ground2.velocityX > 0)) {
     ground2.velocityX = -0.5;
  }
  if (ground3.y>=350 && ground3.velocityY > 0) {
    ground3.velocityY = -0.5;
  }
```

Selbstverständlich colliden auch die Charaktere mit den Grounds.

```
nini.collide(ground);
nini.collide(ground2);
nini.collide(ground3);
elk.collide(ground);
elk.collide(ground2);
elk.collide(ground3);
```

Das letzte Feature ist das Flugzeug, das vorbei fliegt und die Powerups droppt. 

```
//flugzeug
var flugzeug = createSprite(-100, 100);
flugzeug.setAnimation("planeRed1_1");
```

Das Flugzeug erscheint in regelmäßigen Abständen und droppt an einem zufälligen Ort, ein von sechs verschiedenen Powerups ausgewähltes Powerup.

```
function powerups() {
  if (flugzeug.x==abwurf) {
    pup2 = randomNumber(1, 6 );
    powerup.visible = true;
    powerup.x = flugzeug.x;
    powerup.y = flugzeug.y;
    powerup.velocityY = 1.5;
```

In dem Code oben, wird der Abwurf des Powerups beschrieben. Zunächst wird beschrieben wie zufällig ein Powerup von eins bis sechs ausgewählt wird. Dieses wird sichtbar bei der Position des Flugzeugs und erhält eine Geschwindigkeit nach unten. 

In dem unteren Code wird die Auswahl der Abwurfstelle für das Powerup beschrieben. Das Flugzeug erscheint nach 500 Ticks und es wird für den Abwurf eine zufällige X-Koordinate zwischen 100 und 300 gewählt. Das Flugzeug wird sichtbar und erhält eine Geschwindigkeit nach rechts. Wenn das Flugzeug über den rechten Spielfeldrand hinaus geflogen ist, wird es unsichtbar, auf seine Ursprungssituation gesetzt und der Tick-counter auf 0 gesetzt. Eben dieser beginnt von neuen und bei 500 fliegt das Flugzeug erneut.

```
function jet() {
    if (f===500) {
    abwurf = randomNumber(100, 300);
    flugzeug.visible = true;
    flugzeug.velocityX = 3;
  }
    if (flugzeug.x>=450) {
    flugzeug.x=-100;
    flugzeug.velocityX = 0;
    flugzeug.visible = false;
    f = 0;
    drawSprites();
  }
}
```

Fügt man alle diese Commands zusammen, ergibt sich dieses Bild: 

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/Spielfeld.png" alt="image" width="500">


### Die Powerups<a name="Powerup"></a>

Grundsätlich ist es immer sinnvoll powerups einzusammeln. Rote powerups bewirken eine negativen Effekt auf den Gegner, grüne powerups verbessern hingegen den auslösenden Spieler. Aktiviert werden die Powerups, indem ein Spieler den Sprite des powerups berührt. Der powerup wird daraufhin unsichtbar und die pup3(e/n) Variable wird bis 150 erhöht. Solange der Wert kleiner als 150 beträgt, wirkt der gewünschte Effekt. Danach werden die Variabelen pup2 und pup3(e/n) gleich Null gesetzt und der Effekt ist wieder ungültig. So wird dafür gesorgt, dass der jeweilige Effekt nur für eine bestimmte Zeit anhält und die Spieler wieder bereit sind ein neues Powerup aufunehmen. Der Code am Beispiel des Elches als Auslöser:

```
if ((elk.isTouching(powerup)) && (powerup.visible===true)) {
      powerup.visible = false;
      pup3e=1;
    }
    if ((0<pup3e) && (pup3e<150) && (powerup.visible===false)) {
      nini.velocityY = nini.velocityY+10;
      pup3e = pup3e+1;
    }
    if (pup3e===150) {
      pup3e = 0;
      pup2 = 0;
    }
```    


#### Roter BlitzPowerup<a name="RedBolt"></a>

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/RedBolt.png" alt="image" width="100">  

Wenn der Rote Blitz Powerup aktiviert wird, wird der Gegenspieler stark nach unten beschleunigt, was das Springen verhindert:

```
nini.velocityY = nini.velocityY+10;
elk.velocityY = elk.velocityY+10;
```

https://youtu.be/-xrsTx3qcIk


#### Grüner Blitz Powerup<a name="GreenBolt"></a>

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/GreenBolt.png" alt="image" width="100">

Bei der Aktivierung des Grünen Blitz Powerups, werden die Sprungvariablen des auslösenden Spielers gleich Null gesetzt, sodass dieser unbegrenzt springen kann:

```
up = 0;
w = 0;
```

https://youtu.be/-4X9b7YCLho


#### Roter Schild Powerup<a name="RedShield"></a>

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/RedShield.png" alt="image" width="100">

Der Rote Schild Powerup verhindert ein Schießen des Gegenspielers, indem er die "Nachladevariablen" des Gegenspielers gleich Null setzt:

```
q = 0;
e = 0;
      
alt = 0;
shift = 0;
```

https://youtu.be/OFgQbxa9s6o


#### Grüner Schild Powerup<a name="GreenShield"></a>

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/GreenSHield.png" alt="image" width="100">

Wird der grüne Schild Powerup aktiviert, passieren gleich mehrere Dinge. Es werden zum einen die Schussgeschwindigkeit erhöht und die Nachladezeit, durch hohe Werte in den "Nachladevariablen" stark verringert. Außerdem wird der Gegenspieler bei Kontakt mit dem Projektil so versetzt, dass er sofort stirbt:

```
projectile3.velocityX = -30;
      projectile4.velocityX = 30;
      if (projectile3.isTouching(nini)||projectile4.isTouching(nini)){
      nini.x = 300;
      nini.y = 380;
      }
      alt = 100;
      shift = 100;

projectile1.velocityX = -30;
      projectile2.velocityX = 30;
      if (projectile1.isTouching(elk)||projectile1.isTouching(elk)){
      elk.x = 250;
      elk.y = 380;
      }
      q = 100;
      e = 100;
```

https://youtu.be/fRlSWS0Md9c


#### Roter Stern Powerup<a name="RedStar"></a>

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/RedStar.png" alt="image" width="100">

Der Rote Stern Powerup verkleinert den Gegenspieler:
```
nini.scale = 0.05;
      } else {
      nini.scale = 0.15;
elk.scale = 0.05;
      } else {
      elk.scale = 0.15;
```

https://youtu.be/XN6scC1JFoU


#### Grüner Stern Powerup<a name="GreenStar"></a>

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/GreenStar.png" alt="image" width="100">

Der Grüne Stern Powerup vergrößert den auslösenden Spieler:
```
elk.scale = 0.3;
      } else {
      elk.scale = 0.15;

nini.scale = 0.3;
      } else {
      nini.scale = 0.15;
```

https://youtu.be/v8O6ZMtVA8o


### Der Sprung<a name="Sprung"></a>

Der Sprung war das vermutlich langwierigste Element in unserem Spiel. Seit der Festlegung unseres Konzeptes haben wir stetig versucht den Sprung zu verbessern und zu überarbeiten bis zu unserer eigenen Zufriedenheit.
Jetzt sieht der einfache Sprung im Code so aus:

```
 } else if (keyWentDown("up")&&up<2) {
      up = up+1;
      elk.velocityY = -15;
    } else {
      elk.velocityX = 0;
    }
```

Zunächst ist entscheidend, dass bei einer Betätigung der Taste "up", hier in Bezug auf Spieler 2, der Charakter eine Geschwindigkeit von 15 nach oben bekommt, der dann die eingestellte Gravitation entgegenwirkt.
Zusätzlich dazu wird der Variable "up" ein Punkt zugerechnet. Dies ist entscheidend für die Umsetzung des Doppelsprungs, für den wir uns entschieden haben, um das Spiel spannend zu halten und den Spielern die Möglichkeit zu geben sich auch aus kniffeligen Situationen zu retten. In der ersten Zeile des Codes oben ist festgelegt, dass der Sprung nur durchgeführt wird, wenn die Variable "up" einen Wert von unter 2 hat, dass bedeutet, das man nach einem Doppelsprung nicht nocheinmal springen kann solange man in der Luft ist. 
Um die Variable jedoch wieder gleich null zu setzen wird folgender Command benötigt:

```
 if (elk.x >= ground.x-60 && elk.x <= (ground.x+60) && elk.y >= ground.y - 75|| elk.x >= ground2.x-45 && elk.x <= ground2.x+45 && elk.y >= ground2.y-85 || elk.x >= ground3.x-50 && elk.x <= ground3.x+50 && elk.y >= ground3.y-65) {
      up = 0;
```

Im Grunde genommen sagt dieser aus, dass wenn der Elch sich auf einer Plattform befindet, der Wert der Variable gleich null gesetzt wird. Unser erster Ansatz war der Command isTouching, welcher jedoch nur unregelmäßig funktionierte und insgesamt nicht zuverlässig war. In dem Code oben ist nun für jede Plattform der Parameter angegeben, der sicherstellt, das sich der Charakter auf der Plattform befindet. Dies ist zwar umständlich, aber eindeutig verlässlicher als unser erster Ansatz.

https://www.youtube.com/watch?v=GT7GeeBoAlM


### Die Schubserei<a name="Schubserei"></a>

Einer der Kernpunkte unseres Spiels ist das Herunterschubsen des Gegeners von der Plattform. Möglich ist dies durch folgende Zeilen im Code:

```
elk.bounce(nini);
```
 
 und
 
```
nini.bounce(elk);
```

Entgegen unserer ersten Annahme sind diese beiden Zeilen jedoch nicht genug. Um wirklich die gleiche Gewichtung zu haben, so dass nicht einer der beiden Charaktere nicht heruntergeschubst werden kann, muss man beide Zeilen in einer Funktion haben, jedoch durch ein drawSprites getrennt. 


### Das Geschoss<a name="Geschoss"></a>

Die Geschosse sollen den Spielern des Spiels eine weitere Möglichkeit eröffnen den Gegner herunterzuschubsen und somit einen Punkt zu erlangen. Sie sind normale Sprites, die sich ständig unsichtbar auf der Position des zugehörigen Charakters befinden. Pro Charakter sind es zwei Geschosse: Eines für den Schuss nach links und eines für den Schuss nach rechts. 

```
//projectile1
var projectile1 = createSprite(nini.x, nini.y);
projectile1.setAnimation("Bob-Ross.png_1");
projectile1.scale = 0.1;
projectile1.visible=false;
//projectile2
var projectile2 = createSprite(nini.x, nini.y);
projectile2.setAnimation("Bob-Ross.png_1");
projectile2.scale = 0.1;
projectile2.visible=false;
//projectile3
var projectile3 = createSprite(elk.x, elk.y);
projectile3.setAnimation("Bob-Ross.png_1");
projectile3.scale = 0.1;
projectile3.visible=false;
//projectile4
var projectile4 = createSprite(elk.x, elk.y);
projectile4.setAnimation("Bob-Ross.png_1");
projectile4.scale = 0.1;
projectile4.visible=false;
```

Drückt einer der Spieler im Spiel nun eine der beiden Schusstasten (hier "Q" für Spieler 1), so wird noch einmal sichergestellt, dass sich das Geschoss auf der Position des Charakters befindet. Dies kommt insbesondere zur Geltun, wenn der Spieler gerade geschossen hat und das Geschoss technisch noch unterwegs ist. Daraufhin wird es sichtbar und erlangt eine Beschleunigung. Gleichzeitig wird die Variable q gleich null gesetzt, um einen erneuten Schuss überhaupt zu ermöglichen.

```
if (keyWentDown("q")&&q>50&&nini.visible===true) {
          projectile1.x = nini.x;
          projectile1.y = nini.y;
          projectile1.visible = true;
          projectile1.velocityX = -7;
          q = 0;
```

https://www.youtube.com/watch?v=_kips1sJwew


### Der Tod<a name="Tod"></a>

Als "tot" sehen wir einen "Charakter" sobald er eine Y-Koordinate von 360 überschreitet. Geschieht dies passieren einige andere Dinge gleichzeitig. Zunächst werden alle wirkenden Powerups auf dem "toten" Charakter ausgeschaltet, der Text "Player 1/2 died" erscheint, er wird unsichtbar und auf dem Scoreboard erscheint ein Punkt für den Gegner. Der folgende Code ist für den Tod von Spieler 1, für Spieler 2 gibt es den gleichen Code noch einmal.

```
function death() {
  if (nini.y >= 360) {
    pup = 0;
    pup3e = 0;
    fill(rgb(0, 0, 0));
    text("Player 1 died", 110, 150);
    if (nini.visible===true) {
      nini.visible=false;
      scoreelk = scoreelk+1;
    }
```

Zusätzlich dazu geschehen einige andere Dinge in Abhängigkeit der Unsichtbarkeit des Charakters. Zunächst startet ein Timer, der nach 30 Ticks beide Spawnplattformen erscheinen lässt und auf ihnen beide Charaktere sichtbar macht. Ist dies geschehen wird der Timer wieder zurückgesetzt und ist "bereit" für den nächsten Tod Der Timer hilft den Spielern, indem beide Spieler Zeit haben sich auf eine neue Runde vorzubereiten und nicht überrascht sind wenn ihr Charakter plötzlich an einer anderen Stelle erscheint. Vorher gab es Komplikationen, da die Charaktere sehr weit am Rand oder sogar neben den an zufälligen Orten erscheinenden Plattformen gespawnt sind. Wir haben uns auch bewusst entschieden, dass beide Charaktere auf ihrer festen Spawnplattform erscheinen, damit sie nicht ineinander erscheinen. 

```
if (nini.visible===false) {
      dnini = dnini+1;
      if (dnini>30) {
        elk.visible=true;
        nini.visible=true;
        start1.visible = true;
        start2.visible = true;
        nini.x=start1.x;
        nini.y=start1.y-40;
        elk.x=start2.x;
        elk.y=start2.y-40;
        dnini = 0;
      }
    }
```

https://www.youtube.com/watch?v=zwK5xwTkhxk


### Das Scoreboard<a name="Scoreboard"></a>

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/Screenshot%20(36).png" alt="image" width="500">


Das Scoreboard, auf dem die Punkte der Spieler erscheinen, ist ein Rechteck in der rechten oberen Ecke des Spielfelds. In ihm befinden sich zwei Textfelder, zum einen für Spieler 1 und zum anderen für Spieler zwei. Die Punkte der Spieler werden im Rahmen eines Todes, wie oben bereits erläutert, erhöht. Drückt man die Taste "0" werden beide Scores wieder auf 0 gesetzt.

```
fill(rgb(255, 255, 255));
  rect(219, 0, 180, 70);
  fill(rgb(0, 0, 0));
  text("Spieler 2: "+scoreelk, 240, 60);
  text("Spieler 1: "+scorenini, 240, 30);
  drawSprites();
  if (keyDown("0")) {
    scorenini = 0;
    scoreelk = 0;
  }
```


## Herausforderungen<a name="4"></a>

Während unseres Projektes wurden wir mit einigen Herausforderungen konfrontiert, die uns unterschiedlich stark gefordert haben. Das Thema mit dem wir uns vermutlich am längsten beschäftigt haben, war der Sprung. Wir hatten den persönlichen Anspruch diesen möglichst natürlich und dynamisch wirken zu lassen. Die Suche nach der optimalen Lösung hat uns eigentlich eindeutig zu lange beschäftigt.

- Kollision
Weiterbildung

 
## Schlusswort<a name="5"></a>

Wir waren zu Beginn des Projektes sehr unsicher, da wir beide ohne jegliche Erfahrungen im Programmieren in dieses Projekt eingestiegen sind. Bemerkbar hat sich dies bereits bei der Auswahl des richtigen Programmes für uns gemacht, da wir auch auf Grund der sehr frei gestellten Aufgabe nicht von Beginn an ein festes Ziel vor Augen hatten. Diese Startschwierigkeiten relativierten sich mit der gewonnenen Sicherheit im Programm nach einigen Tagen der intensiveren Auseinandersetzung mit diesem. Trotz dessen hatten wir auch nach einigen Wochen keine Konzeptidee von der wir zu 100 Prozent überzeugt waren. Der Durchbruch gelang uns mit der Idee des endgültigen Konzepts und den ersten Vorstellungen eines fertigen Programms. Von diesem Moment an waren wir wieder hochmotiviert und arbeiteten mit viel Spaß an unserem Projekt. Diese Einstellung hat sich bis zum Ende des Projektes durchgezogen und wir waren zum Schluss auf Grund des vielen neuen Wissens, das wir erlangt hatten, in der Lage alle unsere Wünsche umzusetzen. So ergibt sich bei uns trotz des holprigen Starts ein insgesamt sehr positives Endbild über unser Projekt und das Programm "Gamelab", von dem wir zu Beginn auch nicht total überzeugt waren.

# Projektseite "Smooosh"
von Tim Wähner und David Rettmann                                                                   
Stormarnschule Ahrensburg                                                                                             
Klasse 12e                                                                                                       
Schuljahr 18/19                                                                                                       


## Inhalt

[1. Vorwort](#1)                   
[2. Beschreibung](#2)  
[3. Erläuterung](#3)    


## Vorwort<a name="1"></a>

"Smooosh" ist ein Spiel, das im Rahmen des Informatikunterrichts in der 12. Klasse von uns in Gamelab auf code.org programmiert wurde. Wir sind ohne jegliche Erfahrungen im Programmieren in dieses Projekt hineingegangen. Gamelab bot uns in dieser Hinsicht eine gute Plattform, da es eine Blockprogrammiersprache ist und wir dort erste Erfahrungen sammeln und die Anfänge des Programmieren lernen konnten.                                                                                                                  
Das Grundprinzip des Spiels "Smooosh" ist angelehnt an das Spiel "Super Smash Bros.". Es geht darum den Gegenspieler von der Spielfläche herunterzukicken. Unseres unterscheidet sich jedoch in einigen Aspekten erheblich vom Original.                                   
Auf dieser Seite werden wir das Spiel zunächst [beschreiben](#2) und daraufhin die Umsetzung der einzelnen Aspekte näher [erläutern](#3).


## Beschreibung<a name="2"></a>

Startet man unser Spiel, gelangt man zunächst in ein [Startmenü](#Menüs). Um Fortzufahren muss man nun "space" drücken. Damit gelangt man in das [Spielermenü](#Menüs) 1, in dem sich Spieler 1 einen Charakter aussuchen kann, den er spielen möchte. Die Charaktere unterscheiden sich lediglich im Aussehen, aber nicht in den Fähigkeiten. Nachdem er Einen per Mausklick ausgewählt hat, steht Spieler 2 im [Spielermenü](#Menüs) 2 vor der gleichen Entscheidung. Neben den Charakteren wird der Spieler auch mit der Steuerung vertraut gemacht. Haben beide einen Charakter ausgewählt, startet das Spiel.                     
                                                                                                                                       
Die [Steuerung](#Steuerung) für Spieler 1 liegt auf den Tasten "W" für den Sprung, "A" für eine Bewegung nach links, "D" für eine Bewegung nach rechts und "S" für einen noch schnelleren Fall. Für Spieler 2 liegt die Steuerung in der gleichen Formation auf den Pfeiltasten "up", "left", "right" und "down".          
                                                                                                                                      
Im Spiel herrscht eine generelle Beschleunigung nach unten, sprich eine ["Gravitation"](#Gravitation). Die Tasten "S" für Spieler 1 und "down" für Spieler 2 geben dem Charakter einen extra Schub, sodass sie noch schneller fallen.                                          
                                                                                                                                    
Neben den beiden Spielern existieren auf dem ["Spielfeld"](#Spielfeld) eine Sonne in der oberen linken Ecke ohne weitere Funktionen und drei Wolken vor einem hellblauen Hintergrund, die in festgelegten Bereichen an zufälligen Orten erscheinen und die Plattformen bilden, auf denen sich die Charaktere bewegen können. Zwei von ihnen bewegen sich ständig hin und her, eine vertikal und eine horizontal. Die Charaktere der Spieler spawnen jeweils auf einer dieser Plattformen.                                                                 
                                                                                                                                        
Um sich gegenseitig nun von den Plattformen herunterzubekommen, gibt es mehrere Möglichkeiten: Zum einen können die Spieler den [Sprung](#Sprung), oder den Doppelsprung nutzen, um an ihren Gegner heranzukommen und diesen mithilfe des Charakters [herunterzuschubsen](#Schubserei). Zum anderen verfügen beide Spieler über die Möglichkeit den Gegner mit einem [Geschoss](#Geschoss) herunterzuschieben. Für Spieler 1 liegt das Geschoss auf den Tasten ["Q"](#Steuerung), um nach links und ["E"](#Steuerung), um nach rechts zu schießen. Bei Spieler 2 liegt es auf ["Alt"](#Steuerung) für links und ["Shift"](#Steuerung) für rechts. Neben dieser Eigenschaft, die jeder inne hat, gibt es auch [Powerups](#Powerup). Diese werden von einem in regelmäßigen Abständen quer durch das Spielfeld fliegenden Flugzeug abgeworfen und wenn man diese aufsammelt, beeinflusst man entweder sich selber positiv oder den Gegner negativ. Bei diesen Powerups gibt es drei Kategorien. Die erste beeinflusst den Sprung: Sammelt man das [roter Blitz Powerup](#RedBolt) ein, so kann der Gegner für eine kurze Zeit nicht springen und sammelt man das [grüner Blitz Powerup](#GreenBolt) ein, so kann man selber für einen kurzen Zeitraum unendlich oft hochspringen und ist nicht an den Doppelsprung gebunden. Mit den Powerups der zweiten Kategorie wird das Geschoss beeinflusst. Das [roter Schild Powerup](#RedShield) lässt den Gegner für kurze Zeit nicht schießen und das [grüner Schild Powerup](#GreenShield) lässt einen selber unendlich oft schießen und die Projektile bewegen sich schneller für eine kurze Zeit. Die letzte Kategorie verändert die Größe der Charaktere. Das [grüner Stern Powerup](#GreenStar) lässt einen selber wachsen und das [roter Stern Powerup](#RedStar) lässt den Gegner schrumpfen.                                                                                    
                                                                                                                                     
Schafft es nun einer der Spieler, den anderen von einer Plattform herunterzuschieben, sodass er es nicht schafft sich durch einen Sprung zu retten, verschwindet er sobald er das Spielfeld nach unten verlässt. Dies ist im Spiel der [Tod](#Tod). Zur Seite oder nach oben kann das Spielfeld nicht verlassen werden. Auf dem Bildschirm erscheint die Nachricht "Player [1/2] died" und der andere Spieler bekommt auf dem [Scoreboard](#Scoreboard) in der oberen rechten Ecke einen Punkt. Nach einer kurzen Zeit spawnen beide Charaktere wieder auf ihren [Spawnplätzen](#Respawn) und sie können erneut versuchen sich gegenseitig herunterzuschubsen. Möchte man das Scoreboard zurücksetzen, kann man dies mit der Taste ["0"](#Steuerung) tun. Möchte ein Spieler einen anderen Charakter spielen, kann man mit ["space"](#Steuerung) wieder in die Charakterauswahl gelangen.


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









### Die Steuerung<a name="Steuerung"></a>

<img src="https://github.com/BohrisNaturalisRettner/ToDo/blob/master/TAstatur%20endg%C3%BCltig.jpg" alt="image" width="1500">

```
   elk.bounce(nini);
    if ((elk.isTouching(ground)) || (elk.isTouching (ground2)) || (elk.isTouching (ground3))) {
      up = 0;
    }
    if (keyDown("left")) {
      elk.x = elk.x-5;
    } else if ((keyDown("right"))) {
      elk.x = elk.x+5;
    } else if (keyWentDown("up")&&up<2) {
      playSound("sound://category_digital/hop.mp3", false);
      up = up+1;
      elk.velocityY = -15;
    } else {
      elk.velocityX = 0;
    }
    if (keyDown("down")) {
      elk.velocityY = elk.velocityY+10;
    } else {
      elk.velocityY = elk.velocityY + 1;
    }
    drawSprites();
```

``` 
nini.bounce(elk);
    if (keyDown("a")) {
      nini.x = nini.x-5;
    } else if ((keyDown("d"))) {
      nini.x = nini.x+5;
    } else if (keyWentDown("w") && w<2) {
      w = w+1;
      nini.velocityY = -15;
    } else {
      nini.velocityX = 0;
    }
    if (nini.velocityY===0) {
      w = 0;
    }
    if (keyDown("s")) {
      nini.velocityY = nini.velocityY + 10;
    } else {
      nini.velocityY = nini.velocityY + 1;
    }
  }
```

```
if (keyWentDown("q")&&q>50&&nini.visible===true) {
          projectile1.x = nini.x;
          projectile1.y = nini.y;
          projectile1.visible = true;
          projectile1.velocityX = -7;
          q = 0;
    } else if ((keyWentDown("e")&&e>50&&nini.visible===true)) {
        projectile2.x = nini.x;
        projectile2.y = nini.y;
        projectile2.visible = true;
        projectile2.velocityX = 7;
        e = 0;
    } else if (keyWentDown("alt")&&alt>50&&elk.visible===true) {
        projectile3.x = elk.x;
        projectile3.y = elk.y;
        projectile3.visible = true;
        projectile3.velocityX = -7;
        alt = 0;
    } else if (keyWentDown("shift")&&shift>50&&elk.visible===true) {
        projectile4.x = elk.x;
        projectile4.y = elk.y;
        projectile4.visible = true;
        projectile4.velocityX = 7;
        shift = 0;
```

```
 if (keyDown("0")) {
    scorenini = 0;
    scoreelk = 0;
```

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

### Die Gravitation<a name="Gravitation"></a>


### Das Spielfeld<a name="Spielfeld"></a>

### Der Sprung<a name="Sprung"></a>

### Die Schubserei<a name="Schubserei"></a>

### Das Geschoss<a name="Geschoss"></a>

### Die Powerups<a name="Powerup"></a>

#### Roter BlitzPowerup<a name="RedBolt"></a>
Grüner Blitz Powerup<a name="GreenBolt"></a>
Roter Schild Powerup<a name="RedShield"></a>
Grüner Schild Powerup<a name="GreenShield"></a>
Roter Stern Powerup<a name="RedStar"></a>
Grüner Stern Powerup<a name="GreenStar"></a>

### Der Tod<a name="Tod"></a>

### Das Scoreboard<a name="Scoreboard"></a>

### Der Respawn<a name="Respawn"></a>


















## Probleme und Lösungen<a name="4"></a>
jhg

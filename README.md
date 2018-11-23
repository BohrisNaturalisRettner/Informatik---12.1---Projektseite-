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

Startet man unser Spiel, gelangt man zunächst in ein [Startmenü](#Menüs). Um Fortzufahren muss man nun "space" drücken. Damit gelangt man in das [Spielermenü](#Menüs) 1, in dem sich "Player 1" einen Charakter aussuchen kann, den er spielen möchte. Die Charaktere unterscheiden sich lediglich im Aussehen, aber nicht in den Fähigkeiten. Nachdem er Einen per Mausklick ausgewählt hat, steht "Player 2" im [Spielermenü](#Menüs) 2 vor der gleichen Entscheidung. Haben beide einen Charakter ausgewählt, startet das Spiel.                     
                                                                                                                                       
Die [Steuerung](#Steuerung) für "Player 1" liegt auf den Tasten "W" für den Sprung, "A" für eine Bewegung nach links, "D" für eine Bewegung nach rechts und "S" für einen noch schnelleren Fall. Für "Player 2" liegt die Steuerung in der gleichen Formation auf den Pfeiltasten "up", "left", "right" und "down".                                                                                         
                                                                                                                                      
Im Spiel herrscht eine generelle Beschleunigung nach unten, sprich eine ["Gravitation"](#Gravitation). Die Tasten "S" für "Player 1" und "down" für "Player 2" geben dem Charakter einen extra Schub, sodass sie noch schneller fallen.                                          
                                                                                                                                    
Neben den beiden Playern existieren auf dem ["Spielfeld"](#Spielfeld) eine Sonne in der oberen linken Ecke ohne weitere Funktionen und drei Wolken vor einem hellblauen Hintergrund, die in festgelegten Bereichen an zufälligen Orten erscheinen und die Plattformen bilden, auf denen sich die Charaktere bewegen können. Zwei von ihnen bewegen sich ständig hin und her, eine vertikal und eine horizontal. Die Charaktere der Player spawnen jeweils auf einer dieser Plattformen.                                                                 
                                                                                                                                        
Um sich gegenseitig nun von den Plattformen herunterzubekommen, gibt es mehrere Möglichkeiten: Zum einen können die Player den [Sprung](#Sprung), oder den Doppelsprung nutzen, um an ihren Gegner heranzukommen und diesen mithilfe des Charakters [herunterzuschubsen](#Schubserei). Zum anderen verfügen beide Player über die Möglichkeit den Gegner mit einem [Geschoss](#Geschoss) herunterzuschieben. Für "Player 1" liegt das Geschoss auf den Tasten ["Q"](#Steuerung), um nach links und ["E"](#Steuerung), um nach rechts zu schießen. Bei "Player 2" liegt es auf ["Alt"](#Steuerung) für links und ["Shift"](#Steuerung) für rechts. Neben dieser Eigenschaft, die jeder inne hat, gibt es auch [Powerups](#Powerup). Diese werden von einem in regelmäßigen Abständen quer durch das Spielfeld fliegenden Flugzeug abgeworfen und wenn man diese aufsammelt, beeinflusst man entweder sich selber positiv oder den Gegner negativ. Bei diesen Powerups gibt es drei Kategorien. Die erste beeinflusst den Sprung: Sammelt man das [roter Blitz Powerup](#RedBolt) ein, so kann der Gegner für eine kurze Zeit nicht springen und sammelt man das [grüner Blitz Powerup](#GreenBolt) ein, so kann man selber für einen kurzen Zeitraum unendlich oft hochspringen und ist nicht an den Doppelsprung gebunden. Mit den Powerups der zweiten Kategorie wird das Geschoss beeinflusst. Das [roter Schild Powerup](#RedShield) lässt den Gegner für kurze Zeit nicht schießen und das [grüner Schild Powerup](#GreenShield) lässt einen selber unendlich oft schießen für eine kurze Zeit. Die letzte Kategorie verändert die Größe der Charaktere. Das [grüner Stern Powerup](#GreenStar) lässt einen selber wachsen und das [roter Stern Powerup](#RedStar) lässt den Gegner schrumpfen.                                                                                    
                                                                                                                                     
Schafft es nun einer der Player, den anderen von einer Plattform herunterzuschieben, sodass er es nicht schafft sich durch einen Sprung zu retten, verschwindet er sobald er das Spielfeld nach unten verlässt. Dies ist im Spiel der [Tod](#Tod). Zur Seite oder nach oben kann das Spielfeld nicht verlassen werden. Auf dem Bildschirm erscheint die Nachricht "Player [1/2] died" und der andere Spieler bekommt auf dem [Scoreboard](#Scoreboard) in der oberen rechten Ecke einen Punkt. Nach einer kurzen Zeit spawnen beide Charaktere wieder auf ihren [Spawnplätzen](#Respawn) und sie können erneut versuchen sich gegenseitig herunterzuschubsen. Möchte man das Scoreboard zurücksetzen, kann man dies mit der Taste ["0"](#Steuerung) tun. Möchte ein Player einen anderen Charakter spielen, kann man mit ["space"](#Steuerung) wieder in die Charakterauswahl gelangen.


## Erläuterung<a name="3"></a>

### Die Menüs<a name="Menüs"></a>



### Die Steuerung<a name="Steuerung"></a>

```javascript
function movement() {
    elk.bounce(nini);
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
    if (elk.velocityY===0) {
      up = 0;
    }
    if (keyDown("down")) {
      elk.velocityY = elk.velocityY+10;
    } else {
      elk.velocityY = elk.velocityY + 1;
    }
    drawSprites();
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

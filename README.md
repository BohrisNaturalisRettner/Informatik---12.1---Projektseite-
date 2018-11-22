# Projektseite "Smooosh"
von Tim Wähner und David Rettmann, 12e


## Inhalt

[1. Vorwort](#1)                   
[2. Beschreibung](#2)  
[3. Erläuterung](#3)   
[4. Probleme und Lösungen](#4) 


## Vorwort<a name="1"></a>

"Smooosh" ist ein Spiel, das im Rahmen des Informatikunterrichts in der 12. Klasse von uns in Gamelab auf code.org programmiert wurde. Wir sind ohne jegliche Erfahrungen im Programmieren in dieses Projekt hineingegangen. Gamelab bot uns in dieser Hinsicht eine gute Plattform, da es eine Blockprogrammiersprache ist und wir dort erste Erfahrungen sammeln und die Anfänge des Programmieren lernen konnten.
Das Grundprinzip des Spiels "Smooosh" ist angelehnt an das Spiel "Super Smash Bros.". Es geht darum den Gegenspieler von der Spielfläche herunterzukicken. Unseres unterscheidet sich jedoch in einigen Aspekten erheblich vom Original.
Auf dieser Seite werden wir das Spiel zunächst beschreiben, daraufhin die Umsetzung der einzelnen Aspekte erläutern und schließlich auf aufgetretene Probleme und die jeweiligen Lösungen eingehen. 

## Beschreibung<a name="2"></a>

Startet man unser Spiel, gelangt man zunächst in ein Startmenü. Um Fortzufahren muss man nun "space" drücken. Damit gelangt man in das Spielermenü 1, in dem sich "Player 1" einen Charakter aussuchen kann, den er spielen möchte. Die Charaktere unterscheiden sich lediglich im Aussehen, aber nicht in den Fähigkeiten. Nachdem er Einen per Mausklick ausgewählt hat, steht "Player 2" im Spielermenü 2 vor der gleichen Entscheidung. Haben beide einen Charakter ausgewählt, startet das Spiel. Die Steuerung für "Player 1" liegt auf den Tasten "W" für den Sprung, "A" für eine Bewegung nach links, "D" für eine Bewegung nach rechts und "S" für einen noch schnelleren Fall. Für "Player 2" liegt die Steuerung in der gleichen Formation auf den Pfeiltasten "up", "left", "right" und "down". Im Spiel herrscht eine generelle Beschleunigung nach unten, sprich eine "Gravitation". Die Tasten "S" für "Player 1" und "down" für "Player 2" geben dem Charakter einen extra Schub, sodass sie noch schneller fallen. Neben den beiden Playern existieren auf dem "Spielfeld" eine Sonne in der oberen linken Ecke ohne weitere Funktionen und drei Wolken vor einem hellblauen Hintergrund, die in festgelegten Bereichen an zufälligen Orten erscheinen und die Plattformen bilden, auf denen sich die Charaktere bewegen können. Zwei von ihnen bewegen sich ständig hin und her, eine vertikal und eine horizontal. Die Charaktere der Player spawnen jeweils auf einer dieser Plattformen. Um sich gegenseitig nun von den Plattformen herunterzubekommen, gibt es mehrere Möglichkeiten: Zum einen können die Player den Sprung, oder den Doppelsprung nutzen, um an ihren Gegner heranzukommen und diesen mithilfe des Charakters herunterzuschubsen. Zum anderen verfügen beide Player über die Möglichkeit den Gegner mit einem Geschoss herunterzuschieben. Für "Player 1" liegt das Geschoss auf den Tasten "Q", um nach links und "E", um nach rechts zu schießen. Bei "Player 2" liegt es auf "Alt" für links und "Shift" für rechts. Schafft es nun einer der Player, den anderen von einer Plattform herunterzuschieben, sodass er es nicht schafft sich durch einen Sprung zu retten, so stirbt dieser, sobald er das Spielfeld nach unten verlässt. Zur Seite oder nach oben kann das Spielfeld nicht verlassen werden. Auf dem Bildschirm erscheint die Nachricht "Player [1/2] died" und der andere Spieler bekommt auf dem Scoreboard in der oberen rechten Ecke einen Punkt. Nach einer kurzen Zeit spawnen beide Charaktere wieder auf ihren Spawnplätzen und sie können erneut versuchen sich gegenseitig herunterzuschubsen. Möchte man das Scoreboard zurücksetzen, kann man dies mit der Taste "0" tun. 

Ein mögliches Gameplay sieht so aus:


- Startmenü (mit Taste)
- Spielermenü 1 (Auswahl Charaktere)
- Spielermenü 2 (Auswahl Charaktere) 
- Spielstart
- Steuerung Player 1 "wasd" 
- Steuerung Player 2 "Pfeiltasten"
- Gravitation 
- Doppelsprung
- Schüsse
  - Steuerung:
    - Player 1 "q""e"
    - Player 2 "alt" "shift"
  - Verschiebt Spieler 
  - links/rechts
- Tode
  - unten
  - Automatischer Respawn auf einem Block nach 30 Frames
  - Counter 
     - Reset= "0"
  - Todesnachricht 
- Barrier
- Gegenseitige Verschiebung der Spieler
- zufällige Blöcke 
  - bewegen sich
- Flugzeug 
Böden
  - Kollision

## Erläuterung<a name="3"></a>


## Probleme und Lösungen<a name="4"></a>
jhg

# Dice Game
Guide 1 - Players

## Overview
Flödeschemat visar en lösning för att inplemementera ett system som hantera ett godtyckligt antal spelare i ett tärningsspel. Systemet ska hålla reda på spelarnas poäng och växla spelare när deras runda är slut. Här finns också en lösning för att avgöra när en spelare har vunnit spelet, men än så länge delas inte några poäng ut. Det är först senare när poängsystemet är implementerat som vi kan testa logiken för att vinna spelet. Inplementation av poängsystemet kommer att ske i nästa guide.

### Features
* Välja antal spelare
* Struktur för att spara spelarnas poäng
* Avgöra om någon vunnit spelet
* Växla spelare när deras tur är slut

## Visuals
```mermaid
graph TD

Start([Start])-->OutNumPlayer[/Output: Type number of players:/]
OutNumPlayer-->InNumPlayers[/Input numPlayers/]
InNumPlayers-->CreatePlayers[Create int-array scorePlayers,<br/>set size to numPlayers]
CreatePlayers-->CreateCurrentPlayer[Create int curPlayer,<br/>set value to zero]
CreateCurrentPlayer-->CreateWinniongScore[Create int winningScore,<br/>set value to 1000]
CreateWinniongScore-->CreatePlaying[Create bool playing,<br/>set value to true]
CreatePlaying-->GameLoop{playing?}
GameLoop-- No -->GameOver[/Output Press any key to exit/]
GameOver-->EndGame[/Input Read key/]
EndGame-->End([End])
GameLoop-- Yes -->OutputPlayer[/Output<br/> It is Player curPlayer + 1´s turn/]
OutputPlayer-->DecideWinner{"scorePlayers[curPlayer] >= winningScore"}
DecideWinner-- No -->TurnOver[/"Output Player curPlayer + 1,<br/> press any key to end turn!"/]
TurnOver-->InKey2[/Input Read key/]
InKey2-->IncrementPlayer[Increment curPlayer]
IncrementPlayer-->ChangePlayer{curPlayer < numPlayer}
ChangePlayer-- Yes -->GameLoopConector(( ))
ChangePlayer-- No -->ResetPlayer[Set curPlayer to zero]
DecideWinner-- Yes -->PlayingFalse[Set playing to false]
PlayingFalse-->Winner[/Output winner/]
ResetPlayer-->GameLoopConector
GameLoopConector-->GameLoop
Winner-->GameLoopConector
```

## Usage
Öppna projektet. Skriv kod som motsvarara flödesscemat för att implementera lösningen.

### Hints

* Noden *Input numPlayers* beskriver att programmet ska läsa in ett heltal som representerar antalet spelare, heltalet ska sparas i int variabeln *numPlayers*.
* Noden *Playing?* beskriver en while loop som ska fortsätta så länge som variabeln playing är *true*. När en spelare vinner spelet sätts playing till *false* och loopen avslutas.

Var nograna med att testa programet så ofta som möjligt för att se om det fungerar som förväntat.

## Known issues
* Det går inte att testa inpmplementationen av att vinna spelet eftersom poängsystemet inte är implementerat än. Det är först i nästa guide som poängsystemet implementeras.

## Authors
Alve Williamsson



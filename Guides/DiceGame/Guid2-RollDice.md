# Dice Game
Guide 2 - Roll Dice

## Overview
Flödesschemat visar en lösning för att implementera ett system som hantera tärningsslag och poängberäkning. Varje runda slås fem tärningar och poängen beräknas utifrån tärningarnas värden. En slagen etta ger 100 poäng och en femma ger 50 poäng. Alla andra tärningsvärden ger inga poäng. Poängen för rundan läggs till spelarens totala poäng och när en spelare når 1000 poäng vinner den spelaren spelet.

### Features
* Slå fem tärningar
* Ge spelaren poäng baserat på tärningarnas värden

## Visuals

```mermaid
graph TD

%% Start
Start([Start])-->OutNumPlayer[/Output: Type number of players:/]
OutNumPlayer-->InNumPlayers[/Input numPlayers/]
InNumPlayers-->CreatePlayers[Create int-array scorePlayers,<br/>set size to numPlayers]
CreatePlayers-->CreateCurrentPlayer[Create int curPlayer,<br/>set value to zero]
CreateCurrentPlayer-->CreateWinniongScore[Create int winningScore,<br/>set value to 1000]
CreateWinniongScore-->CreateGameDice[Create int numGameDice,<br/>set to five]
CreateGameDice-->CreateAvailableDice[Create int availableDice,<br/>set to numGameDice]
CreateAvailableDice-->CreateturnScore[Create int turnScore,<br/>set to zero]
CreateturnScore-->CreateRandom[Create Random random,<br/>set to new Random]
CreateRandom-->CreatePlaying[Create bool playing,<br/>set value to true]

%% Gameloop
CreatePlaying-->GameLoop{playing?}
GameLoop-- No -->GameOver[/Output Press any key to exit/]
GameOver-->EndGame[/Input Read key/]
EndGame-->End([End])
GameLoop-- Yes -->OutputPlayer[/Output<br/> It is Player curPlayer + 1´s turn/]
OutputPlayer-->ResetturnScore[Set turnScore to zero]
ResetturnScore-->InKey[/Input Read key/]
InKey-->PressToRoll[/"Output Press any key to roll dice!"/]

%% RollLoop
PressToRoll-->CreateI[Create int i, set to zero]
CreateI-->RollLoop{i < availableDice}
RollLoop-- Yes -->Roll[Generate random number 1-6]
Roll-->OutNumber[/Output random number/]
OutNumber-->Score{Score?}
Score-- 1 -->One[Add 100 to turnScore]
Score-- 5 -->Five[Add 50 to turnScore]
Score-- 2,3,4,6 -->IncrementI[Increment i]
One & Five -->IncrementI
IncrementI -->RollLoop

%% End turn
RollLoop-- no -->AddScoreToPlayer["Add turnScore to<br/>scorePlayers[curPlayer]"]
AddScoreToPlayer-->OutputturnScore[/"Output Player curPlayer + 1,<br/>turnScore"/]
OutputturnScore-->OutPlayerScore[/"Output Player curPlayer + 1,<br/>scorePlayers[curPlayer]"/]
OutPlayerScore-->DecideWinner{"scorePlayers[curPlayer] >= winningScore"}

%% Change player
DecideWinner-- No -->TurnOver[/"Output Player curPlayer + 1,<br/> press any key to end turn!"/]
TurnOver-->InKey2[/Input Read key/]
InKey2-->IncrementPlayer[Increment curPlayer]
IncrementPlayer-->ChangePlayer{curPlayer < numPlayer}
ChangePlayer-- Yes -->GameLoopConector(( ))
ChangePlayer-- No -->ResetPlayer[Set curPlayer to zero]

%% Win
DecideWinner-- Yes -->PlayingFalse[Set playing to false]
PlayingFalse-->Winner[/Output winner/]
ResetPlayer-->GameLoopConector
GameLoopConector-->GameLoop
Winner-->GameLoopConector

classDef newNode stroke:green,stroke-width:5px
classDef modNode stroke:blue,stroke-width:5px

class CreateNumDice,CreateAvailableDice,CreateturnScore,CreateRandom,ResetturnScore,CreateI,RollLoop,Roll,OutNumber,Score,One,Five,IncrementI,OutputturnScore,AddScoreToPlayer,PressToRoll,InKey,OutPlayerScore,CreateGameDice newNode

%%class OutputPlayer,TurnOver modNode

```

## Usage
Utgå från er tidigare lösning och lägg till de nya funktionerna med hjälp av flödesschemat. 
* Nya noder är markerade med grön färg.

### Hints
* För att slå fem tärniningar används en for-loop. De tre noderna *Create i set to zero*, *i < numGameDice* och *Increment i* beskriver for-loopen.
* Noden *Generate random number 1-6* motsvarat ett tärningsslag. För att lösa det ska programmetgenerera ett slumptal mellan 1 och 6. Loppen upprepar sedan denna process fem gånger.
* Noden *Score?* beskriver de if-satser som avgör om tärningsslaget ger poäng eller inte. Om tärningen visar en etta läggs 100 poäng till turnScore och om tärningen visar en femma läggs 50 poäng till turnScore. För övriga resultat av tärnningsslaget behövs inga if-satser då de inte ger några poäng.

Testa programmet ofta för att se om det fungerar som förväntat.

## Known issues
* Om användaren matar in ett ogiltigt värde för antal spelare (t.ex. en sträng eller ett negativt tal) kommer programmet att krascha. 

## Authors
Alve Williamsson

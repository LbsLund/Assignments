# Dice Game - Guide 3
Guid för implementation av omslag av tärningar i tärningsspelet

## Overview
Flödesschemat visar en lösning för att implementera ett system för att slå om tärningar. Om en spelare slår en etta eller en femma kan spelaren välja att slå om tärningarna som inte gav poäng. Poängen för rundan läggs till spelarens totala poäng och när en spelare når 1000 poäng vinner den spelaren spelet.

### Features
* First feature
* Second feature

## Visuals

```mermaid
graph TD

%% Start
Start([Start])-->OutNumPlayer[/Output: Type number of players:/]
OutNumPlayer-->InNumPlayers[/Input numPlayers/]
InNumPlayers-->CreatePlayers[Create int-array scorePlayers,<br/>set size to numPlayers]
CreatePlayers-->CreateCurrentPlayer[Create int curPlayer,<br/>set value to zero]
CreateCurrentPlayer-->CreateWinningScore[Create int winningScore,<br/>set value to 1000]
CreateWinningScore-->CreateGameDice[Create int numGameDice,<br/>set to five]
CreateGameDice-->CreateAvailableDice[Create int availableDice,<br/>set to numGameDice]
CreateAvailableDice-->CreateTurnScore[Create int turnScore,<br/>set to zero]
CreateTurnScore-->CreateRandom[Create Random random,<br/>set to new Random]
CreateRandom-->CreatePlaying[Create bool playing,<br/>set value to true]

%% Game loop
CreatePlaying-->GameLoop{playing?}
GameLoop-- No -->GameOver[/Output Press any key to exit/]
GameOver-->EndGame[/Input Read key/]
EndGame-->End([End])
GameLoop-- Yes -->OutputPlayer[/Output<br/> It is Player curPlayer + 1´s turn/]
OutputPlayer-->ResetTurnScore[Set turnScore to zero]
ResetTurnScore-->ResetAvailableDice[Set availableDice to numGameDice]
ResetAvailableDice-->CreateTurnActive[Create bool turnActive,<br/>set value to true]
CreateTurnActive-->TurnLoop{turnActive?}


%% TurnLoop
RollLoop-- no -->SubAv[Subtract scoreDice from availableDice]
SubAv-->Out[/Output Player curPlayer + 1<br/>rollScore/]
Out-->RollScoreGZero{rollScore > 0}
RollScoreGZero-- Yes -->RollToTurnScore[Add rollScore to turnScore]
RollToTurnScore-->OTurnScore[/Output Player curPlayer + 1,<br/>turnScore/]
OTurnScore-->OutTurn[/"Output Player curPlayer + 1,<br/>availableDice,<br/> Roll Again?"/]
OutTurn-->RollAgain{RollAgain?}
RollScoreGZero-- No -->TurnScoreZero[Set turnScore to zero]
TurnScoreZero-->RAvailableDice[Set availableDice to numGameDice]
RAvailableDice-->NoScore[/Output Player curPlayer + 1<br/>turn score is zero!/]
NoScore-->TurnLoopFalse[Set turnActive to false]
RollAgain-- Yes -->OutputRollScore[/"Output Player curPlayer + 1,<br/> scorePlayers[curPlayer]"/]
TurnLoopFalse-->OutputRollScore
RollAgain-- No -->TurnToPlayerScore["Add turnScore to<br/>scorePlayers[curPlayer]"]
TurnToPlayerScore-->TurnLoopFalse
OutputRollScore-->TurnLoop

%% RollLoop
TurnLoop-- Yes -->PressToRoll[/"Output Press any key to roll dice!"/]
PressToRoll-->InKeyRoll[/Input Read key/]
InKeyRoll-->CreateRollScore[Create int rollScore,<br/>set value to zero]
CreateRollScore-->CreateScoreDice[Create scoreDice,<br/>set to zero]
CreateScoreDice-->CreateI[Create int i, set to zero]
CreateI-->RollLoop{i < availableDice}
RollLoop-- Yes -->Roll[Generate randomNumber 1-6]
Roll-->OutNumber[/Output randomNumber/]
OutNumber-->Score{Score?}
Score-- 1 -->One[Add 100 to rollScore]
Score-- 5 -->Five[Add 50 to rollScore]
Score-- 2,3,4,6 -->IncrementI[Increment i]
One & Five -->IncrementScoreDice[Increment scoreDice]
IncrementScoreDice-->IncrementI
IncrementI -->RollLoop

%% Change player
TurnLoop-- No -->DecideWinner{"scorePlayers[curPlayer] >= winningScore"}
DecideWinner-- No -->TurnOver[/"Output Player curPlayer + 1,<br/>, press any key to end turn!"/]
TurnOver-->InKey2[/Input Read key/]
InKey2-->IncrementPlayer[Increment curPlayer]
IncrementPlayer-->ChangePlayer{curPlayer < numPlayer}
ChangePlayer-- Yes -->GameLoopConnector((( )))
ChangePlayer-- No -->ResetPlayer[Set curPlayer to zero]

%% Win
DecideWinner-- Yes -->PlayingFalse[Set playing to false]
PlayingFalse-->Winner[/Output winner/]
ResetPlayer-->GameLoopConnector
GameLoopConnector-->GameLoop
Winner-->GameLoopConnector

classDef newNode stroke:green,stroke-width:5px
classDef modNode stroke:blue,stroke-width:5px

class CreateTurnActive,TurnLoop,ResetAvailableDice,CreateRollScore,DecrementAvailable,Out,RollScoreGZero,RollToTurnScore,SubDice,AvailableDiceZero,ReAvailableDice,OutReroll,NoScore,TurnLoopFalse,TurnScoreZero,RAvailableDice,OutTurn,RollAgain newNode

class One,Five,OTurnScore,OutputRollScore,TurnToPlayerScore modNode

```

## Usage
Utgå från er tidigare lösning och lägg till de nya funktionerna med hjälp av flödesschemat. 
* Nya noder är markerade med grön färg.
* Modifierade noder är markerade med blå färg.

### Hints
* Variabeln *turnScore* håller koll på poängen som genereras på en runda. 
* Variabeln *rollScore* håller koll på poängen som genereras varje tärningsslag, efter ett slag adderas *rollScore* till *turnScore*. 
* Variabeln *availableDice* håller koll på hur många tärningar som är tillgängliga att slå, *availableDice* subtraheras med 1 för varje tärning som ger poäng. 
* Om *rollScore* är noll när alla tillgängliga tärningar är slagna sätts *turnScore* till noll och spelarens tur avslutas.
* Om *rollScore* inte är noll när alla tillgängliga tärningar är slagna kan spelaren välja att slå om de tillgängliga tärningarna, men riskerar då att få noll i *rollScore* och därmed noll i *turnScore*.
* Istället för att slå om kan spelaren välja att spara *turnScore* i *scorePlayer[curPlayer]*, poäng som sparats på detta vis kan inte försvinna.

Testa programmet ofta för att se om det fungerar som förväntat.

## Known issues
* Om användaren matar in ett ogiltigt värde för antal spelare (t.ex. en sträng eller ett negativt tal) kommer programmet att krascha. 

## Authors
Alve Williamsson

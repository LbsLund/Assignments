# Födelse
Variabler, övning 3

## Uppgift

Skriv ett program som frågar efter användarens ålder och nuvarande år. Programmet skriver sedan ut årtalet som personen är född.

### Indata

Första raden tar emot ett heltal som anger vad personen fyller i år. Andra raden tar emot nuvarande år som heltal.

### Utdata

Skriv ut `Du föddes: ÅRTAL`, ersätt ÅRTAL med året då personen föddes.
### Exempel

**Input**

```text
10
2000
```

**Output**

```text
Du föddes: 1990
```

### Förklaring

Läs in åldern och nuvarande år, omvandla dessa till heltal. Subtrahera sedan åldern från nuvarande år. Skriv ut meddelandet och födelseår som text genom att konvertera heltalet till string-data med hjälp av `str()`. 

Exempel:
```python
myInt = 1990
print("Du föddes: " + str(myInt))
```

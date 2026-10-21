# Omvänd ordning
Loopar, övning 4

## Uppgift

Skriv ett program som läser in ett positivt heltal N och skriver ut alla heltal från N till och med 0, ett tal per rad. Talen ska alltså skrivas ut i fallande ordning. 
### Indata

Ett positivt heltal N.

### Utdata

Skriv ut talen från N till 0, ett tal per rad.

### Exempel

**Input**

```text
5
```

**Output**

```text
5
4
3
2
1
0
```

### Förklaring

Använd en for-loop som går baklänges med hjälp av `reverse()` börjar vid N + 1 och fortsätter till och med 0. Tänk på att `range()`behöver stå innanför parenteserna i reverse.
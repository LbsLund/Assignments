# Medelvärde
Datastrukturer, övning 2

## Uppgift

Skriv ett program som läser in N tal och skriver ut både summan och medelvärdet.

### Indata

Första raden består av tal separerade med mellanrum. Talen kan vara decimaltal med punkt som decimaltecken.

### Utdata

Skriv ut `Summa: X` och `Medelvärde: Y` på varsin rad.

### Exempel

**Input**

```text
2.5 3.5 9.0
```

**Output**

```text
Summa: 15.0
Medelvärde: 5.0
```

### Förklaring

Spara talen i en lista. Skapa en float-variabel som börjar på 0. Gå igenom talen i listan och lägg till varje tal till summan. När loopen är klar dividerar ni summan med antalet tal i listan. Ni kan kan använda `len()` för att ta reda på hu många tal som finns i listan, skriv listan innanför parenteserna. 
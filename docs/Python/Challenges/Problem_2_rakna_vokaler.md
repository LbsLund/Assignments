# Problem 2

## Räkna vokaler

Du får en textrad. Räkna hur många vokaler den innehåller. Vokalerna är a, e, i, o, u, y, å, ä och ö. Stora och små bokstäver räknas likadant.

### Indata

Ta emot en textrad.

### Utdata

Skriv ut antalet vokaler.

### Exempel

**Input**

```text
Programmering är kul
```

**Output**

```text
6
```

### Förklaring

 Ta emot texten som en string och omvandl den till små bokstäver. Dela inte upp den med hjälp av split. Skapa en string för alla vokaler. Gå igenom varje vokal och se hur många gånger den förekommer i texten. Spara sedan en siffra som håller spara det högsta talet.

 Exempel
```Python
numVowels = 0
vowels = "aei..."
text = input("Input words: ").lower()

for x in vowels:
    text.count(x)
```

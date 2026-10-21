# Bubble Sort
Sortering, övning 1

## Uppgift
Skriv ett program som sorterar en lista med heltal i stigande ordning med hjälp av **Bubble sort**. Använd **inte** `sort()` eller `sorted()`.

### Indata
Första raden består av heltal separerade med mellanrum.

### Utdata
Skriv ut talen i stigande ordning, varje tal på ny rad.

### Exempel

**Indata**
```text
5 1 4 2 8
```

**Utdata**
```text
1
2
4
5
8
```

### Förklaring och steg-för-steg-tips
Bubble sort jämför tal som ligger bredvid varandra och byter plats på dem om de ligger i fel ordning.

1. Gå igenom listan från början till slut.
2. Jämför varje tal med talet direkt efter.
3. Om det första talet är större än det andra, byt plats på dem.
4. Efter en genomgång har det största talet som återstår flyttats längst åt höger.
5. Upprepa genomgångarna tills listan är sorterad.

Du kan använda en yttre loop för antalet genomgångar och en inre loop för jämförelserna. Tänk på att den inre loopen ska stanna innan listans sista index.

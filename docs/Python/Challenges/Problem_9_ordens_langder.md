# Problem 9

## Ordens längder

Skriv ut varje ord i en mening tillsammans med dess längd. Räkna därefter hur många ord som innehåller minst fem tecken.

### Indata

Ta emot en textrad.

### Utdata

Skriv varje ord och längd på en egen rad. Skriv sist antalet ord med minst fem tecken enligt exemplet.

### Exempel

**Input**

```text
Jag gillar programmering
```

**Output**

```text
Jag: 3
gillar: 6
programmering: 13
Antal ord med minst 5 bokstäver: 2
```

### Förklaring

Gå igenom orden ett i taget. Använd len() för att hitta längden. Öka en räknare för varje ord som har minst fem tecken.

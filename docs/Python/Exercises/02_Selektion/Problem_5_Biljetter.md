# Biljettpris
Selektion, övning 5

## Uppgift
Skriv ett program som läser in en persons ålder och skriver ut priset på en biljett.

Priserna är:
- Under 7 år: gratis, 0 kr
- 7–17 år: 30 kr
- 18–64 år: 60 kr
- 65 år eller äldre: 30 kr

### Indata
En heltalsålder.

### Utdata
Biljettpriset följt av ` kr`, till exempel `30 kr`.

### Exempel

**Indata**
```text
72
```

**Utdata**
```text
30 kr
```

### Förklaring och tips
Använd `if`, `elif` och `else` för att kontrollera åldern i ordning.
Börja med åldrarna under 7, fortsätt sedan med åldrarna under 18 och under 65. De som är 65 eller äldre hamnar i det sista fallet.

Förutsätt att indatan är en giltig, icke-negativ ålder.

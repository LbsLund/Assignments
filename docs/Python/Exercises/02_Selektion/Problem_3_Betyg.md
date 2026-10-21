# Betyg
Selektion, övning 3

## Uppgift
Skriv ett program som läser in en poäng mellan 0 och 100 och skriver ut motsvarande betyg enligt tabellen.

### Indata
Ett heltal mellan 0 och 100.

### Utdata
Betyget enligt följande gränser:

| Poäng | Betyg |
|---|---|
| 90–100 | A |
| 80–89 | B |
| 70–79 | C |
| 60–69 | D |
| 0–59 | F |

### Exempel

**Indata**
```text
84
```

**Utdata**
```text
B
```

### Förklaring och tips
Använd en kedja med `if`, `elif` och `else`. Börja med den högsta gränsen:
- Om poängen är minst 90 blir betyget A.
- Annars, om poängen är minst 80 blir betyget B.
- Fortsätt på samma sätt för C och D.
- Om ingen av gränserna uppfylls blir betyget F.

Du behöver inte kontrollera den övre gränsen i varje steg, eftersom tidigare villkor redan har fångat upp högre poäng.

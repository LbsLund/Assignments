# Inloggning
Selektion, övning 4

## Uppgift
Skriv ett program som kontrollerar ett användarnamn och ett lösenord.

Det korrekta användarnamnet är `elev` och det korrekta lösenordet är `python123`.

### Indata
Två rader:
1. Användarnamn
2. Lösenord

### Utdata
- Skriv `Välkommen!` om både användarnamnet och lösenordet är korrekta.
- Annars skriver programmet `Fel användarnamn eller lösenord.`

### Exempel

**Indata**
```text
elev
python123
```

**Utdata**
```text
Välkommen!
```

### Förklaring och tips
Använd `if` och operatorn `and`.
Villkoret ska bara vara sant om användarnamnet **och** lösenordet stämmer.

Exempel på jämförelse:
```python
if name is "elev" and password is "python123":
```
Använd `else` för alla andra kombinationer.

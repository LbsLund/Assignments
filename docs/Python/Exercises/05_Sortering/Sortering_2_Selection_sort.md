# Selection sort
Sortering, övning 2

## Uppgift
Skriv ett program som sorterar en lista med heltal i stigande ordning med hjälp av **Selection sort**. Använd **inte** `sort()` eller `sorted()`.

### Indata
Första raden består av heltal separerade med mellanrum.

### Utdata
Skriv ut talen i stigande ordning, varje tal på ny rad.

### Exempel

**Indata**
```text
29 10 14 37 13
```

**Utdata**
```text
10 
13 
14 
29 
37
```

### Förklaring och steg-för-steg-tips
Selection sort letar efter det minsta talet i den osorterade delen av listan och placerar det först i den delen.

1. Börja vid listans första position.
2. Leta igenom resten av listan efter det minsta talet.
3. Spara indexet där det minsta talet finns.
4. Byt plats på det minsta talet och talet på den aktuella positionen.
5. Flytta till nästa position och upprepa.

Efter varje steg blir den sorterade delen en position längre. Du behöver en loop för positionerna och en inre loop för att hitta det minsta talet.

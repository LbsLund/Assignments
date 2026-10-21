# Triangel
Selektion, övning 6

## Uppgift
Skriv ett program som läser in längden på en triangels tre sidor. Avgör om triangeln är liksidig, likbent eller oliksidig.

I den här uppgiften behöver du bara klassificera sidorna utifrån om några sidlängder är lika. Du behöver inte kontrollera om sidorna faktiskt kan bilda en triangel.

### Indata
Tre positiva heltal, ett per rad.

### Utdata
- Skriv `Liksidig`om alla sidlängder är lika.
- Skriv `Likbent` om minst två sidlängder är lika.
- Skriv `Oliksidig` om alla tre sidlängder är olika.

### Exempel

**Indata**
```text
4
4
6
```

**Utdata**
```text
Likbent
```

### Förklaring och tips
Skapa `if` och `elif`-satser, använd `and` och `or` för att skapa villkoren.

Är triangeln liksidig:
- Den första **och** den andra **och** den tredje sidan är lika långa.  

Om triangeln inte är liksidig, undersök om den är likbent:
- den första sidan är lika lång som den andra, **eller**
- den första sidan är lika lång som den tredje, **eller**
- den andra sidan är lika lång som den tredje.

Om inget av dessa villkor stämmer är alla sidor olika långa.

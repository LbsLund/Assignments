# Bokstav
Datastrukturer, övning 4

## Uppgift

Skriv ett program som läser ett ord och sedan en bokstav. Skriv ut Ja om bokstaven finns i ordet och Nej om den inte gör det.

### Indata

Första raden innehåller ett ord. Andra raden innehåller en bokstav.

### Utdata

Skriv ut `Ja` om bokstaven finns i ordet och `Nej` om den inte gör det. 

### Exempel

**Input**

```text
Programmering
g
```

**Output**

```text
Ja
```

### Förklaring

En string fungerar som en lista av chars, där en char är ett tecken i samlingen. Använd `in`för att kolla om bokstaven finns i ordet. använd `lower()` för att göra om texten till små bokstäver.

Exempel:
```python
word = "Python".lower()
letter = 't'
if letter in word:
```

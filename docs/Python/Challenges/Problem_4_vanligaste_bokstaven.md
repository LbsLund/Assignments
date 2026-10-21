# Problem 4

## Vanligaste bokstaven

Du får en textrad. Hitta den bokstav som förekommer flest gånger. Mellanslag ignoreras. Vid lika många förekomster ska bokstaven som kommer först i alfabetet väljas.

### Indata

Ta emot en textrad.

### Utdata

Skriv ut den vanligaste bokstaven.

### Exempel

**Input**

```text
banan
```

**Output**

```text
a
```

### Förklaring

Spara en heltalsvariabel för högst antal bokstäver och ge den värdet 0, skapa en charvariabel för bokstaven och ge den värdet 'a'. Gör om texten till små bokstäver, efter er input skriver ni .lower(). Gå igenom alfabetets bokstäver och räkna hur många gånger varje bokstav finns i texten. Använd .count() efter texten och skicka i bokstaven i parentesen. när ni hittar en bokstav som förekommer fler gånger än det sparade talet, skrivern ni över talet med det nya största talet, sedan skriver ni över er char med den nya bokstaven. Skriv ut bokstaven med högst antal förekomster.

Exempel
```Python
letterCount = 0
letter = 'a'
alphabet = "abcd...."
```

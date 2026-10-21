# Algoritmer 6

## Är talet ett primtal?

Ett primtal är ett heltal större än 1 som endast kan delas jämnt med `1`
och sig självt.

Skriv ett program som avgör om ett givet tal är ett primtal.

En enkel algoritm är att prova att dela talet med alla heltal från `2`
upp till talet före det självt. Om någon division går jämnt upp är talet
inte ett primtal.

### Indata

En rad innehåller ett heltal `n`.

`n` är mellan `2` och `100 000`.

### Utdata

Skriv ut `JA` om talet är ett primtal och `NEJ` annars.

### Exempel

**Input**

``` text
17
```

**Output**

``` text
JA
```

### Förklaring

17 kan inte delas jämnt med något heltal mellan 2 och 16. 17 är därför
ett primtal.

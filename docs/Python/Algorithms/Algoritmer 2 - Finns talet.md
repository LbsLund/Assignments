# Algoritmer 2

## Finns talet?

Du får en lista med heltal och därefter ett tal som du ska leta efter.

Skriv ett program som undersöker om talet finns i listan.

Ett enkelt sätt att lösa problemet är att börja med det första talet och
jämföra det med talet du letar efter. Om det inte stämmer går algoritmen
vidare till nästa tal. Detta fortsätter tills talet hittas eller hela
listan har undersökts.

Detta kallas **linjär sökning**.

### Indata

Den första raden innehåller ett heltal `n`, antalet tal.

Den andra raden innehåller `n` heltal.

Den tredje raden innehåller heltalet som ska sökas efter.

### Utdata

Skriv ut `JA` om talet finns i listan och `NEJ` annars.

### Exempel

**Input**

``` text
6
4 12 7 19 3 8
19
```

**Output**

``` text
JA
```

### Förklaring

Algoritmen undersöker talen i ordning: `4 → nej`, `12 → nej`, `7 → nej`,
`19 → ja`. Talet hittades och svaret blir därför `JA`.

# Algoritmer 1

## Störst

Du får en lista med heltal. Din uppgift är att hitta det största talet i
listan.

Det går naturligtvis att lösa problemet genom att använda Pythons
inbyggda funktion `max()`, men målet med uppgiften är att själv skapa en
algoritm som hittar det största talet.

Algoritmen kan exempelvis börja med att anta att det första talet är
störst. Därefter undersöker den talen ett efter ett. Om den hittar ett
tal som är större än det hittills största talet, sparas detta som det
nya största talet.

Hjälp till att skriva ett program som hittar det största talet.

### Indata

Den första raden innehåller ett heltal `n`, antalet tal.

Den andra raden innehåller `n` heltal.

Alla tal är mellan `-1000` och `1000`.

### Utdata

Skriv ut det största talet i listan.

### Exempel

**Input**

``` text
5
4 17 2 23 8
```

**Output**

``` text
23
```

### Förklaring

Programmet börjar med `4` som det största talet. Sedan jämförs talen ett
i taget. Det största talet är därför `23`.

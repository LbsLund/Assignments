# Algoritmer 4

## Näst störst

Du får en lista med olika heltal.

Ditt uppdrag är att hitta det **näst största** talet.

Problemet liknar uppgiften att hitta det största talet, men algoritmen
behöver nu hålla reda på två värden.

När ett nytt tal undersöks kan tre saker hända: talet är större än det
största talet, talet är mindre än det största men större än det näst
största, eller talet är mindre än båda.

Hjälp till att skriva ett program som hittar det näst största talet.

### Indata

Den första raden innehåller ett heltal `n`.

Den andra raden innehåller `n` olika heltal.

`n` är minst 2.

### Utdata

Skriv ut det näst största talet.

### Exempel

**Input**

``` text
6
4 17 2 23 8 11
```

**Output**

``` text
17
```

### Förklaring

Det största talet är `23`. Det näst största talet är `17`.

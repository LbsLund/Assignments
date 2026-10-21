# Algoritmer 5

## Växel

Du arbetar i en butik och ska hjälpa kunderna att räkna ut vilken växel
de ska få tillbaka.

Butiken använder mynten:

``` text
1 kr
2 kr
5 kr
10 kr
20 kr
50 kr
```

Du får veta hur mycket pengar kunden ska få tillbaka.

För att använda så få mynt som möjligt ska du först använda så många
stora mynt som möjligt. Därefter fortsätter du med nästa största mynt.

### Indata

En rad innehåller ett heltal `n`, summan pengar som ska lämnas tillbaka.

`n` är mellan `1` och `1000`.

### Utdata

Skriv ut det minsta antal mynt som behövs.

### Exempel

**Input**

``` text
87
```

**Output**

``` text
5
```

### Förklaring

Algoritmen kan använda `50 + 20 + 10 + 5 + 2 = 87`. Det behövs alltså 5
mynt.

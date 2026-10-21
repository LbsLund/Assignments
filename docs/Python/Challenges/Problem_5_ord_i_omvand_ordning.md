# Problem 5

## Ord i omvänd ordning

Du får en textrad. Skriv ut orden i omvänd ordning, men behåll bokstävernas ordning inom varje ord.

### Indata

En rad innehåller minst ett ord. Orden separeras av exakt ett mellanslag.

### Utdata

Skriv ut orden i omvänd ordning, separerade av ett mellanslag.

### Exempel

**Input**

```text
Python är ganska roligt
```

**Output**

```text
roligt ganska är Python
```

### Förklaring

I Python går det att skriva ut en lista bakläng hjälp av en omvänd for-loop. 

Exempel
```Python
for x in reversed(words):
```

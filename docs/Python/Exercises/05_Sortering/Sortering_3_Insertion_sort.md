# Insertion sort
Sortering, övning 3

## Uppgift
Skriv ett program som sorterar en lista med heltal i stigande ordning med hjälp av **Insertion sort**. Använd **inte** `sort()` eller `sorted()`.

### Indata
Första raden består av heltal separerade med mellanrum.

### Utdata
Skriv ut talen i stigande ordning, varje tal på ny rad.

### Exempel

**Indata**
```text
7 4 5 2 9
```

**Utdata**
```text
2 
4 
5 
7 
9
```

### Förklaring och steg-för-steg-tips
Insertion sort bygger upp en sorterad del av listan genom att sätta in ett tal på rätt plats.

1. Tänk att det första talet redan är sorterat.
2. Nästa tal i listan kollar sedan om det är större eller mindre än talet före och placerar sig på rätt plats.
3. Jämför sedan det tredje talet med de två första talen och placerar det på rätt plats.
4. Upprepa tills alla tal har behandlats.

Sorterade delen av listan:
| Index | Värde |
|---|---|
| 1 | 4 |
| 2 | 5 |
| 3 | 7 |

Osorterade delen av listan:
| Index | Värde |
|---|---|
| 4 | 2 |
| 5 | 9 |

Efter de två första iterationerna är de tre första talen sorterade. I nästa iteration kollar vi på index 4 och hittar värdet 2, det ska placeras först i listan.

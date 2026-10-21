# Problem 7

## Är orden anagram?

Två ord är anagram om de innehåller exakt samma bokstäver lika många gånger, men i olika ordning. 

### Indata

Två rader, en med varje ord.

### Utdata

Skriv ut JA om orden är anagram och NEJ annars.

### Exempel

**Input**

```text
listen
silent
```

**Output**

```text
JA
```

### Förklaring

Du kan sortera bokstäverna i båda orden och jämföra resultaten.

 Exempel
```Python
word = input("Input word: ")
print(sorted(word))
```

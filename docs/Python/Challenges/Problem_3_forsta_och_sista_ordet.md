# Problem 3

## Första och sista ordet

Du får en textrad. Skriv ut det första och det sista ordet i raden.

### Indata

Ta emot en textrad.

### Utdata

Skriv ut det första ordet och det sista ordet i raden.

### Exempel

**Input**

```text
äpple päron banan kiwi mango
```

**Output**

```text
äpple mango
```

### Förklaring

Dela upp orden i en lista. Anänd sedan index 0 för att skriv ut första ordet. I Python går det att använda negativa index i listor, negativa index börjar bakifrån, index -1 blir då sista elementet i listan. 

Exempel
```Python
words = input("Input words: ").split()
print(words[-1])
```

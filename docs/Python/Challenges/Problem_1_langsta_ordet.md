# Problem 1

## Längsta ordet

Du får en textrad. Hitta det längsta ordet i textraden. Skriv ut antalet tecken i det längsta ordet.

### Indata

Ta emot en textrad.

### Utdata

Skriv ut antalet tecken i det längsta ordet.

### Exempel

**Input**

```text
sol programmering katt bil
```

**Output**

```text
13
```

### Förklaring

Börja med att spara ett heltal för länden på det första ordet. Gå igenom resten av orden och byt talet när du hittar ett längre ord. Använd len() för att ta reda på längden av ordet.

 Exempel
```Python
for x in words:
    len(x)
```

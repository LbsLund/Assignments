# Quick sort
Sortering, övning 4

## Uppgift
Skriv ett program som sorterar en lista med heltal i stigande ordning med hjälp av **Quick sort**. Använd **inte** `sort()` eller `sorted()`.

### Indata
Första raden består av heltal separerade med mellanrum.

### Utdata
Skriv ut talen i stigande ordning, varje tal på ny rad.

### Exempel

**Indata**
```text
8 3 1 7 0 10
```

**Utdata**
```text
0 
1 
3 
7 
8 
10
```

### Förklaring
**Funktioner**  
Funktioner är kodblock som går att återanvända med hjälp av anrop. I Python definieras funktioner med hjälp av nyckelordet `def` sedan funktionens namn, sedan en parameterlista som skapas med hjälp av parenteser `()`. I parameterlistan kan vi skicka in information till funktionen. Efter parentesen kommer kolon `:`. Efterföljande indenterade rader kommer att tillhöra metodens kropp, koden i kroppen körs när funktionen anropas. Kroppen kan innehålla en retur-sats, den skapas med hjälp av nyckelordet `return`. Efter return anger vi vad funktionen ska returnera. Vi anropar en metod genom att skriva namnet följt av parameterlistan, i parameterlistan skickar vi med nödvändig information.

Exempel på definition av funktion:
```Python
def double(number):
  return number * 2
```
Exempel på anrop av funktion:
```Python
myNumber = double(myNumber)
```

**Rekursion**  
Rekursion innebär att en funktion anropar sig själv för att bryta ner ett stort problem i mindre, enklare delar. Varje rekursiv funktion behöver ett basfall som stoppar anropen, samt ett rekursivt fall där funktionen körs igen med ett mindre värde.

**Quick sort**  
Quick sort delar upp problemet i mindre delar genom att välja ett **pivotvärde**. Det går att använda det första talet i listan som pivot

Skapa en funktion som tar emot en lista.

I funktionen:
1. Returnera listan om dess längd är ett eller mindre (basfall).
1. Välj ett pivotvärde.
2. Dela upp de övriga talen i två nya listor: tal som är mindre än eller lika med pivot och tal som är större än pivot.
3. Ropa på funktionen rekursivt, en gång för listan med mindre tal och en gång för listan med större tal (rekursiva fall).
4. Returnera resultatet av anropet med mindre tal + pivot + resultatet av anropet med större tal

När rekursionen är färdig returneras en sorterad lista.

**Exempel, med metoden quick_sort:**
Indata: numbers = [5 3 9  4 8]  
Anrop: quick_sort(numbers)


**Anrop 1:**  
pivot: [5]  
mindre: [3, 4]  
större: [9, 8]  
Anrop 2: quick_sort(mindre)  
Anrop 3: quick_sort(större)  
retur: mindre[3, 4] + pivot[5] + större[8, 9]


**Anrop 2:**  
pivot: [3]  
mindre: [-]  
större: [4]  
Både listan mindre och större utlöser nu basfallet och skapar därför inga nya rekursioner.  
retur: mindre[-] + pivot[3] + större[4]

**Anrop 3:** 
pivot: [9]  
mindre: [8]  
större: [-]  
Både listan mindre och större utlöser nu basfallet och skapar därför inga nya rekursioner.  
retur: mindre[8] + pivot[9] + större[-]


# Programmeringsbegrepp i Python

## Datatyp

En **datatyp** beskriver vilken sorts värde något är. Vanliga datatyper
är `int` (heltal), `float` (decimaltal), `str` (text), `bool`
(sant/falskt) och `list` (samling av värden).

|Datatyper|Värde|Beskrivning|
|--|--|--|
|int|17|Heltal|
|float|21.5|Decimaltal|
|str|"Hello"|Text|
|bool|True|Sant/Falskt|
|list|[ "apple", "banana" ]|En samling av värden|


## Variabel

En **variabel** är en typ av behållare som används för att spara och komma åt ett
värde. Värden kan ändras under programmets gång.

``` python
points = 10
points = 15
print(points)  # 15
```

## Operator

En **operator** utför en operation eller jämförelse på värden.

Aritmetiska operatorer: `+`, `-`, `*`, `/`, `//` (heltalsdivision) och
`%` (modulo - rest vid division).

``` python
number = 4 + 2
print(number)  # 6

remainder = 5 % 2
print(remainder)   # 1
```

Jämförelseoperatorer jämför värden och ger `True` eller `False`, till
exempel `==`, `!=`, `<`, `>`, `<=`, `>=`, `is` och `is not`.

``` python
age = 17
print(age >= 18)  # False
print(age == 17)  # True
```

## Selektion

**Selektion** innebär att programmet väljer vilka instruktioner som ska
köras beroende på ett villkor. I Python används `if`, `elif` och `else`.

``` python
age = 17

if age >= 18:
    print("Adult")
elif age >= 13:
    print("Teenager")
else:
    print("Child")
```

-   `if` testar det första villkoret.
-   `elif` testar ett nytt villkor om tidigare villkor inte stämde.
-   `else` körs om inget tidigare villkor stämde.

## Indentering

**Indentering** betyder att kodrader får ett indrag från
vänstermarginalen. I Python visar indenteringen vilka rader som hör
ihop, exempelvis vilka instruktioner som tillhör en if-sats eller loop.

``` python
age = 17

if age >= 18:
    print("You are an adult.")

print("The program continues.")
```

De två indenterade raderna tillhör `if`-satsen. Python använder normalt
fyra mellanslag per indenteringsnivå.

## Datastruktur

En **datastruktur** är ett sätt att organisera och lagra flera värden
tillsammans. Datastrukturer skapar samlingarEn lista (`list`) är en vanlig datastruktur.

``` python
fruits = ["apple", "banana", "pear"]
print(fruits)
print(fruits[0])  # apple
```

## Index

Ett **index** anger positionen för ett värde i en ordnad datastruktur,
till exempel en lista eller sträng. I Python börjar index på **0**.

``` python
colors = ["red", "green", "blue"]
print(colors[0])  # red
print(colors[2])  # blue

word = "Python"
print(word[1])     # y
```

## Loopar och iteration

**Iteration** betyder att instruktioner upprepas. **Loopar** används för att
genomföra iterationer.

En `for`-loop kan upprepa instruktioner ett bestämt antal gånger:

``` python
for number in range(3):
    print(number)
```

En `while`-loop upprepar instruktioner så länge ett villkor är sant:

``` python
counting = True
count = 0 
while counting:
    count += 1
    if count >= 3:
        counting = False

```

## Funktion och metod

En **funktion** utför en specifik instruktion. Den anropas med sitt namn och parenteser efter. Funktionen kan ta emot värden som argument i parenteserna och returnera ett värde.

Funktionen `print()` skriver ut värden på skärmen.

``` python
print("Hello, world!")
```
En **metod** är en funktion som tillhör ett objekt, till exempel en sträng eller lista. Metoder anropas med punktnotation.

Metoden `split()` tillhör strängar och delar upp en sträng till en lista av ord:

``` python
text = "apple banana pear"
fruits = text.split()
print(fruits)  # ['apple', 'banana', 'pear']
```


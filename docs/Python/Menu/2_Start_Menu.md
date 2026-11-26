# 2. Start Menu

## Målet

Klienten ska visa en meny med alternativen Log in och Exit. Variabeln `menu` håller reda på vilken meny som ska visas.

Lägg till efter att klienten tagit emot välkomstmeddelandet:

```python
menu = "Start Menu"

clientActive = True
while clientActive:

    match menu:

        case "Start Menu":
            os.system('cls')

            print(menu + "\n")
            menuOptions = ["Log in", "Exit"]

            for x in range(len(menuOptions)):
                print(x + 1, menuOptions[x])

            selected = int(input()) - 1
            menu = menuOptions[selected]
```

## Hur fungerar `match`?

`match` jämför värdet i `menu` med olika `case`. När ett case passar körs dess kod.

```python
match menu:
    case "Start Menu":
        # Visa startmenyn
    case "Log in":
        # Hantera inloggning
    case "Exit":
        # Avsluta
```

När användaren väljer ett alternativ ändras `menu`. Nästa varv i loopen kör det case som passar det nya värdet.

## Varför match?

Det går också att använda `if`, `elif` och `else`. `match` kan däremot göra menystrukturer tydliga när det finns många alternativ och olika programlägen.

På klienten används `match` för att styra användargränssnittet och vilket flöde programmet ska följa.

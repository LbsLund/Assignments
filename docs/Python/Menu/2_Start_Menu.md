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

Exempel:
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

## Extra: `os.system('cls')`

Klientkoden använder:

```python
import os
os.system('cls')
```

- `os` är en Python-modul för funktioner som samverkar med operativsystemet.
- `system()` kör ett kommando via operativsystemets kommandotolk.
- `cls` rensar terminalfönstret i Windows.

Det påverkar bara terminalens utseende – inte anslutningen eller programmets data. På macOS och Linux används normalt `clear` i stället.

## Testa

1. Starta `server.py`.
2. Starta `client.py` i ett annat terminalfönster.
3. Klienten visat *Start Menu* med valen: *Log in* och *Exit*.
4. Användaren kan välja ett alternativ, men inget mer händer.
5. Inga nya menyer visas ännu, det kommer i senare guider!



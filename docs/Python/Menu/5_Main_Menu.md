# 5. Main Menu

## Målet

Efter lyckad inloggning ska klienten byta till en huvudmeny. I denna första version innehåller den bara Exit.

Lägg till följande case i klientens `match`:

```python
case "Main Menu":

    print(menu + "\n")
    menuOptions = ["Exit"]

    for x in range(len(menuOptions)):
        print(x + 1, menuOptions[x])

    selected = int(input()) - 1
    menu = menuOptions[selected]
```

När inloggningen lyckas sätts `menu` till `Main Menu`. Nästa varv i loopen visar därför huvudmenyn.

Om användaren väljer Exit ändras `menu` till `Exit`, och Exit-caset skickar kommandot till servern.

## Varför separata menyer?

När programmet växer kan huvudmenyn få fler alternativ utan att startmenyn behöver bli mer komplicerad. Exempel på framtida alternativ:

```python
menuOptions = [
    "View balance",
    "Deposit currency",
    "Transaction history",
    "Log out",
    "Exit"
]
```

Varje alternativ kan få ett eget `case` eller leda vidare till en ny meny.

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

## Att tänka på

- Servern hanterar en klient i taget i den här versionen.
- `loggedIn` finns på servern; klienten kan inte själv bestämma att den är inloggad.
- Lösenordet `admin` är bara ett undervisningsexempel, inte säker lösenordshantering.
- Socketar skickar bytes. `encode()` gör text till bytes och `decode()` gör bytes till text.
- TCP är en byte-ström och garanterar inte att ett `recv()` motsvarar ett helt meddelande i större program.

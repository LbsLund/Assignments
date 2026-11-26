# 5. Main Menu

## Målet

Efter lyckad inloggning ska klienten byta till en huvudmeny. I denna första version innehåller den bara Exit.

Lägg till följande case i klientens `match`:

```python
case "Main Menu":

    os.system('cls'
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

## Att tänka på

- Servern hanterar en klient i taget i den här versionen.
- `loggedIn` finns på servern; klienten kan inte själv bestämma att den är inloggad.
- Lösenordet `admin` är bara ett undervisningsexempel, inte säker lösenordshantering.
- Socketar skickar bytes. `encode()` gör text till bytes och `decode()` gör bytes till text.
- TCP är en byte-ström och garanterar inte att ett `recv()` motsvarar ett helt meddelande i större program.

## Testa

1. Starta `server.py`.
2. Starta `client.py` i ett annat terminalfönster.
3. Klienten visat *Start Menu* med valen: *Log in* och *Exit*.
4. När användaren väljer *Log in* visas den menyn.
5. Om användaren anger rätt lösenord skriver klienten ut meddelandet *success*, tryck på valfri tangent för att komma vidare.
6. *Main Menu* visas med valet: *Exit*.
7. När användaren väljer *Exit* så stängs kopplingen mellan klient och server.
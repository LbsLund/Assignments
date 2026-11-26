# 4. Log in

## Målet

Klienten skickar Log in. Servern frågar efter lösenord och kontrollerar om det är rätt. I denna övning är lösenordet `admin`.

## Client

Lägg till detta case:

```python
case "Log in":

    os.system('cls')
    print(menu + "\n")

    client.sendall(menu.encode())
    message = client.recv(4096).decode()
    print(message, end=' ')

    message = input()
    client.sendall(message.encode())

    message = client.recv(4096).decode()
    print(message)

    if message == "success":
        menu = "Main Menu"
    else:
        menu = "Start Menu"
    
    input("Press any key to continue...")
```

## Server

Servern behöver hålla reda på inloggningsstatus:

```python
case ("Log in", False):

    client.sendall("Password:".encode())
    password = client.recv(4096).decode()

    if password == "admin":
        loggedIn = True
        client.sendall("success".encode())
    else:
        client.sendall("fail".encode())
```

## Matcha två värden

`match (request, loggedIn)` matchar en tuple med två värden. Servern tar hänsyn både till kommandot och om användaren är inloggad.

| request | loggedIn | Vad händer? |
|---|---|---|
| `Log in` | `False` | Fråga efter lösenord |
| `Log in` | `True` | Matchar inte inloggningsfallet |
| `Exit` | `False` | Avsluta anslutningen |
| `Exit` | `True` | Avsluta anslutningen |
| Annat | Valfritt | `case _` hanterar det |

## Vad betyder `True | False`?

```python
case ("Exit", True | False):
```

`True | False` betyder att värdet får vara antingen True eller False. Det är ett OR-mönster. Exit kan därför hanteras oavsett om användaren är inloggad.

## Varför är match användbart på servern?

Servern måste tolka kommandon och kontrollera om användaren får utföra dem. Att matcha flera värden samtidigt är praktiskt när fler funktioner läggs till, exempelvis saldo, insättning och transaktionshistorik. Klienten kan visa menyer, men servern ska alltid kontrollera behörighet.

## Testa

1. Starta `server.py`.
2. Starta `client.py` i ett annat terminalfönster.
3. Klienten visat *Start Menu* med valen: *Log in* och *Exit*.
4. När användaren väljer *Log in* visas den menyn.
5. Om användaren anger rätt lösenord skriver klienten ut meddelandet *success*, tryck på valfri tangent för att komma vidare, inget mer händer.
6. Om användaren anger fel lösenord skriver klienten ut meddelandet: *fail*, tryck på valfri tangent för att komma vidare, *Start Menu* visas.

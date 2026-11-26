# 4. Log in

## Målet

Klienten skickar Log in. Servern frågar efter lösenord och kontrollerar om det är rätt. I denna övning är lösenordet `admin`.

## Client

Lägg till detta case:

```python
case "Log in":

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
```

## Server

Servern behöver hålla reda på inloggningsstatus:

```python
loggedIn = False

clientActive = True
while clientActive:

    request = client.recv(4096).decode()

    match (request, loggedIn):

        case ("Log in", False):

            client.sendall("Password:".encode())
            password = client.recv(4096).decode()

            if password == "admin":
                loggedIn = True
                client.sendall("success".encode())
            else:
                client.sendall("fail".encode())

        case ("Exit", True | False):

            client.sendall("Disconnected from server".encode())
            client.close()
            clientActive = False

        case _:

            client.sendall("error".encode())
            print("Invalid Request:", request, "Logged in:" loggedIn)
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

# 3. Exit

## Målet

När användaren väljer Exit ska klienten skicka kommandot till servern. Servern svarar och anslutningen stängs.

## Client

Lägg till ett case:

```python
case "Exit":

    client.sendall(menu.encode())

    message = client.recv(4096).decode()
    print(message)

    client.close()
    clientActive = False
```

Variabeln `menu` innehåller nu texten `Exit`, så den kan skickas till servern.

## Server

Servern behöver ta emot kommandot och hantera det:

```python
loggedIn = False

clientActive = True
while clientActive:

    request = client.recv(4096).decode()

    match (request, loggedIn):

        case ("Exit", True|False):

            client.sendall("Disconnected from server".encode())
            client.close()
            clientActive = False
        case _:
            
            client.sendall("error".encode())
            print("Invalid Request:", request, "Logged in:", loggedIn)
```

Detta är en förenklad variant. I nästa steg utökas serverns match så att den också kontrollerar inloggningsstatus.

## Avsluta båda sidor

Klienten skickar Exit, servern svarar, servern stänger sin socket och klienten tar emot svaret och stänger sin socket.

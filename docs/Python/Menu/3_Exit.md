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
```

Variabeln `menu` innehåller nu texten `Exit`, så den kan skickas till servern.

## Server

Servern behöver ta emot kommandot och hantera det:

```python
loggedIn = False

while client.fileno() != -1:

    request = client.recv(4096).decode()

    match request:
        case "Exit":
            client.sendall("Disconnected from server".encode())
            client.close()
        case _:
            client.sendall("error".encode())
```

Detta är en förenklad variant. I nästa steg utökas serverns match så att den också kontrollerar inloggningsstatus.

## Vad betyder `client.fileno() != -1`?

`fileno()` hämtar socketens filbeskrivare från operativsystemet, ett heltal som identifierar socketen.

- En öppen socket returnerar normalt ett heltal, exempelvis `3`.
- En socket som stängts lokalt returnerar `-1`.

Villkoret betyder alltså ungefär: **fortsätt så länge socketen inte har stängts lokalt**.

Det är inte en säker kontroll av att nätverksförbindelsen fungerar. Om motparten kopplas bort kan filnumret fortfarande vara giltigt tills ett send- eller recv-anrop upptäcker felet.

## Avsluta båda sidor

Klienten skickar Exit, servern svarar, servern stänger sin socket och klienten tar emot svaret och stänger sin socket.

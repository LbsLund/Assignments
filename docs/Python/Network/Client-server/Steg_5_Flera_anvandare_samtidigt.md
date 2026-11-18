# Steg 5 - Flera användare samtidigt

## Mål

Nu ska servern kunna hantera flera klienter samtidigt. I steg 3 väntade
servern på att en klient skulle bli färdig innan nästa accepterades. Nu
får varje klient en egen **tråd** (*thread*).

## Vad är en tråd?

En tråd är en separat körningsväg i ett program. Serverns huvudtråd ska
fortsätta att acceptera nya anslutningar. Varje klient får en egen tråd
som hanterar just den klientens kommunikation.

En klient som väntar på användarens inmatning behöver då inte hindra
andra klienter från att ansluta.

## Uppgift A - Importera threading

Lägg till:

``` python
import threading
```

Modulen ingår i Python.

## Uppgift B - Skapa en funktion för klienthantering

Flytta lösenordskontrollen och meddelandehanteringen till en funktion,
exempelvis:

``` python
def handle_client(client_socket, address):
    print("Client connected:", address)

    # Handle password and messages here

    client_socket.close()
```

Se till att klientens socket stängs när klienten lämnar eller om ett fel
uppstår. Du kan använda `try` och `finally` för att säkerställa att
stängningen sker.

## Uppgift C - Starta en tråd för varje klient

I serverns huvudloop ska du: 1. Vänta på en klient med `accept()`. 2.
Skapa en tråd som kör `handle_client`. 3. Skicka med klientens socket
och adress som argument. 4. Starta tråden. 5. Gå tillbaka och vänta på
nästa klient.

Exempel:

``` python
thread = threading.Thread(
    target=handle_client,
    args=(client_socket, address)
)

thread.start()
```

### Varför tuple i args?

`args` ska innehålla argumenten som skickas till funktionen. Därför
används en tuple:

``` python
args=(client_socket, address)
```

Tuplen innehåller två värden. Kommat är viktigt.

-   `target=handle_client` anger vilken funktion tråden ska köra.
-   Skriv inte `target=handle_client()` -- då anropas funktionen direkt
    i stället för att skickas till tråden.
-   `thread.start()` startar tråden.

## Uppgift D - Testa flera klienter samtidigt

Du behöver inte flera datorer. Använd flera terminalfönster på samma
dator.

1.  Starta servern.
2.  Starta klienten i terminal 2 och logga in.
3.  Låt klienten vara ansluten utan att skriva `Exit`.
4.  Starta en ny klient i terminal 3.
5.  Kontrollera att även den andra klienten kan ansluta och logga in.
6.  Avsluta klienterna oberoende av varandra.

## Förståelsefrågor

1.  Vad är en tråd?
2.  Varför får varje klient en egen tråd?
3.  Vad gör `thread.start()`?
4.  Vad är skillnaden mellan `target=handle_client` och
    `target=handle_client()`?
5.  Varför får varje klient en egen socket från `accept()`?
6.  Vad kan bli problematiskt om flera trådar ändrar samma variabel
    samtidigt?

## Utmaning - räkna anslutna användare

Lägg till en räknare som ökar när en klient ansluter och minskar när en
klient lämnar. Fundera på varför ett `threading.Lock` kan behövas när
flera trådar ändrar samma räknare.
# Steg 1 - Skapa server och klient

## Mål

Skapa två program som kommunicerar, en server och en klient. Servern skapas i filen `server.py` och klienten i `client.py. Först startas servern som väntar på en anslutning, sedan startar klienten som ansluter till servern. Klient och server ska kunna skicka information mellan varandra. Programmen körs på **samma dator**, i två olika terminalfönster.

## Begrepp

-   **Klient:** programmet som tar initiativ till anslutningen.
-   **Server:** programmet som klienten ansluter till.
-   **Socket:** programmets gränssnitt för nätverkskommunikation.
-   **IP-adress:** anger vilken dator kommunikationen
    ska till.
-   **Port:** anger vilken tjänst på datorn kommunikationen ska till.
-   **TCP:** transportprotokoll som ger en ordnad byteström.
-   **Tuple:** en ordnad samling av värden. 

## Förberedelser

Skapa två nya Python-filer:

``` text
server.py
client.py
```

Använd IP-adressen `127.0.0.1`. Den pekar på **den egna datorn** och
kallas loopback eller localhost.

Vi använder port `5000`. Det är ett valt portnummer för övningen,
Python kräver inte just 5000. Det är ett praktiskt högt portnummer för
egna testprogram. Servern och klienten måste använda samma port.
Om port 5000 redan används kan ni välja exempelvis 5001, men ändra då i
båda programmen.

## Uppgift A - Servern

1.  Importera socket `import socket`.
2.  Skapa en socket variabel och döp den till *server* `server = socket.socket()`.
3.  Använd *bind()* för att koppla servern till IP-adressen. Gör en tuple av IP-adressen och portnumret`server.bind(("127.0.0.1", 5000))`
4.  Anropa `server.listen()` så att servern börjar lyssna efter anslutningar.
5.  Använd `print()` för att skriva ut texten *Server waiting for a client...* till konsolen.
6.  Anropa *accept* för att vänta på en klient, spara klientens socket och adress i två olika variabler `client, address = server.accept()`.
7.  Använd *print()* för att skriva ut att klienten har anslutit och klientens adress`print("Client connected: ", address)` till konsolen.
8.  Använd *sendall* för att skicka  texten *Connected to server* till klienten, glöm inte att konvertera strängen tll bytes `client.sendall("Connected to server".encode())`.
9.  Ta emot text från klienten, glöm inte att konvertera strängen tll bytes `message = client.recv(4096).decode()`
10.  Använd `print()` för att skriva ut meddelandet frå klienten till konsolen.
11.  Använd *sendall* för att skicka texten*Disconnected from server* till klienten `client.sendall("Disconnected from server".encode())`.
12.  Stäng anslutningen till klienten `client.close()`
13.  Stäng klienten `client.close()`. 
14.  Använd `print()` för att skriva ut texten *Client disconnected from server* till konsolen.
14.  Stäng servern `server.close()`

## Uppgift B - Klienten
1.  Importera socket `import socket`.
2.  Skapa en socket variabel och döp den till *client* `client = socket.socket()`.
3.  Anslut till servern med IP-nummer: *127.0.0.1* och port *5000* `client.connect(("127.0.0.1",5000))`.
4.  Ta emot meddelande från servern `message = client.recv(4096).decode()`.
5.  Skriv ut meddelandet med hjälp av `print()`. 
5.  Låt användaren skriva ett meddelande med hjälp av `input()` spara meddelandet in en variabel som ni döper till *message*.
6.  Skicka meddelandet till servern, glöm inte att konvertera till bytes `client.sendall(message.encode())`.
7.  Ta emot ett meddelande från servern, glöm inte att göra om från bytes till sträng `message = client.recv(4096).decode()`.
8.  Skriv ut meddelandet med hjälp av `print()`.
9.  Stäng klienten `client.close()`.

## Testa

1.  Starta `server.py` i ett terminalfönster.
2.  Starta `client.py` i ett annat.
3.  Kontrollera att klienten får meddelandet *Connected to server*.
4.  Skriv ett meddelande.
5.  Kontrollera att klienten får meddelandet *Disconnected from server*.

Servern hanterar bara en klient i detta steg. Starta om servern för att
testa en ny anslutning.

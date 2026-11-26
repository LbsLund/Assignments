# 1. Client and Server

## Målet
Först ska klienten kunna ansluta till servern. Servern accepterar anslutningen och skickar ett välkomstmeddelande.

## Client – Ansluter till server

Skapa `client.py`:

```python
import socket
import os

client = socket.socket()
client.connect(("127.0.0.1", 5000))

message = client.recv(4096).decode()
print(message)
```

- `socket.socket()` skapar en socket.
- `connect()` ansluter till servern. 
- `recv(4096)` tar emot upp till 4096 bytes vid detta anrop. 
- `decode()` gör om bytes till text.

## Server – Lysnar efter och tar emot anslutningar från klient

Skapa `server.py`:

```python
import socket

server = socket.socket()
server.bind(("127.0.0.1", 5000))
server.listen()

print("Server waiting for a client...")

client, address = server.accept()
print("Client connected: ", address)
client.sendall("Connected to server".encode())
```

- `bind()` anger IP-adress och port.
- `listen()` gör servern redo att ta emot anslutningar.
- `accept()` väntar på en klient och returnerar socketen samt klientens adress.
- `sendall()` skickar data. `encode()` gör om text till bytes.

`127.0.0.1` betyder den egna datorn. Port `5000` är porten som används.

## Testa

1. Starta `server.py`.
2. Starta `client.py` i ett annat terminalfönster.
3. Klienten ska skriva ut `Connected to server`.

Servern måste startas först.

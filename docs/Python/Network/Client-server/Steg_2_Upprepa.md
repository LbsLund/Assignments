# Steg 2 - Upprepa

## Mål

Bygg vidare på projektet. Servern nu kunna ta emot flera meddelande.

## Uppgift A - Ändra servern

1.  Skapa variabeln *message* efter att klienten anslutit servern `message = ""`
2.  Skapa sedan en while-loop som kör så länge *message* inte får värdet "exit.
3.  Första raden inuti while-loopen tar ni emot ett meddelande från klienten `message = client.recv(4096).decode()`.
4.  Nästa rad i while-loopen Skriv ut meddelandet med hjälp av `print()`.

## Uppgift B - Ändra klienten

1.  Efter att klienten anslutit servern skapar ni en while-loop som kör så länge *message* inte får värdet "exit.
2.  Första raden inuti while-loopen tar ni emot ett meddelande från användaren `message = input("Type message: ")`.
3.  Nästa rad i while-loopen skickar meddelandet till servern.

## Testa

1.  Starta server.
2.  Starta klienten.
3.  Kontrollera så att klienten anslutit till servern.
4.  Skicka mer än ett meddelande till servern.
5.  Skicka *exit* till servern.
6.  Kontrollera så att klienten anslutning till servern avslutas.

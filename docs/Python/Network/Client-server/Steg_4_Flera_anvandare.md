# Steg 4 - Flera användare

## Mål

I tidigare steg kunde servern bara hantera en klient. Nu ska servern
fortsätta vänta på nya klienter utan att behöva startas om.

Servern ska fortfarande hantera **en klient åt gången**.

## Vad behöver ändras?

1.  Servern väntar på en klient med `accept()`.
2.  Servern hanterar klientens lösenord och meddelanden.
3.  Klienten skriver `exit` och anslutningen stängs.
4.  Servern går tillbaka till början av loopen.
5.  Servern väntar på nästa klient.

## Uppgift A - Ändra servern

1.  Efter `listen()` Skapa en while-loop som gör att servern fortsätter att köras.
2.  Placera all resterande kod inuti while-loopen, förutom `server.close()`.
3.  Stäng klientens socket när sessionen avslutas.
4.  Loopen börjar om och nästa klient kan ansluta.


## Uppgift B - Ändra klienten

Klienten behöver inte ändras i det här steget, utan kan se ut som i tidigare steg.

## Testa

1.  Starta servern en gång.
2.  Starta klienten, logga in med `admin` och skicka meddelanden.
3.  Avsluta med `exit`.
4.  Starta klienten igen.
5.  Kontrollera att den andra klienten kan ansluta utan att servern
    startas om.
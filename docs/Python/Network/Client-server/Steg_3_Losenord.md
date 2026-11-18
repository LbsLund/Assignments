# Steg 3 - Lösenord

## Mål

Bygg vidare på projektet. Servern ska kräva lösenordet *admin* innan
klienten får använda tjänsten.

Om lösenordet är rätt skickar kan klienten skicka meddelande till servern. Om det är fel skickar servern *Access denied* och stänger anslutningen.

Anslutningen har redan skapats när lösenordet
kontrolleras. Lösenordet avgör alltså om klienten får använda tjänsten,
inte om själva nätverksanslutningen kan skapas.

**OBS** detta är ingen säker hantering av ett lösenord!

## Uppgift A - Ändra servern

1.  När klienten anslutit ska servern skicka texten *Password:* till klienten.
2.  Servern tar emot lösenordet från klienten.
3.  Jämför lösenordet med `"admin"`.
4.  Om lösenordet är rätt: Skicka texten *Access granted*, fortsätt till meddelandeloopen.
5.  Om lösenordet är fel: Skicka texten *Access denied* till klienten och stäng anslutningen.

## Uppgift B - server.close()

1.  
2.  Efter att klienten anslutit till servern ta emot `"Password:"`.
3.  Skriv ut *Password:*.
3.  Låt användaren skriva in lösenordet 
5.  Skicka lösenordet till servern.
4.  Ta emot serverns svar.
5.  Om svaret är `Access granted`, fortsätt till meddelandeloopen.
6.  Om svaret är `Access denied`, avsluta klienten.

## Tips

En if-sats kan kontrollera lösenordet:

``` python
if password == "admin":
    # Send the access granted message
else:
    # Send the access denied message
```

## Testa

-   Anslut och skriv rätt lösenord: `admin`.
-   Anslut igen och skriv ett felaktigt lösenord.
-   Kontrollera att servern ger olika svar.

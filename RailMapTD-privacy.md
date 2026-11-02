# RailMapTD — privacy en gegevensgebruik

Bijgewerkt: 2 november 2026.

Deze toelichting beschrijft het gegevensgebruik in de huidige broncode van de mobiele RailMapTD-app voor iOS en Android en de gekoppelde horloge-apps. De afzonderlijke Windows PhotoTagger valt buiten deze toelichting.

## Gegevens op je apparaat

RailMapTD bewaart projecten, geocodes, gedownloade spoor- en objectdata, geïmporteerde ScopeTD-gegevens, foto's, eventuele originelen en fotometadata lokaal. Metadata kan onder meer datum en tijd, GPS-positie, nauwkeurigheid, kilometrering, spoornaam, kijkrichting, tags, scopegegevens en opmerkingen bevatten.

De app bewaart instellingen lokaal. Voor ProRail hosted data worden gebruikersnaam, token en aanmaaktijd opgeslagen. Het wachtwoord voor het aanvragen van een token wordt niet opgeslagen. Een token is een toegangsgegeven: deel het niet met anderen.

Foto's en vrije tekst kunnen personen of vertrouwelijke werkgegevens bevatten. Controleer daarom de inhoud voordat je deze deelt. Het uitschakelen van een veld in de foto-overlay verwijdert dat veld niet automatisch uit de onderliggende metadata of export.

## Netwerkverkeer en ontvangers

| Functie | Ontvanger en gegevens |
| --- | --- |
| Projectdata ophalen of verversen en geocodes zoeken | ProRail ArcGIS ontvangt de aanvraag, waaronder geselecteerde geocodes of zoektekst en, voor afgeschermde diensten, het token. |
| Token aanvragen | De ProRail-tokenservice ontvangt de ingevoerde gebruikersnaam en het wachtwoord via HTTPS om een token te maken. |
| Kaart en luchtfoto | De gebruikte kaartdienst, waaronder ProRail/Georizon en Kadaster/PDOK, ontvangt aanvragen voor het getoonde kaartgebied. Het aangevraagde gebied kan iets zeggen over je werkgebied of locatie. Apple-kaartweergaven gebruiken daarnaast Apple-diensten. |
| Optionele treinnadering | NS Virtual Train ontvangt de actuele breedte- en lengtegraad, zoekradius en API-authenticatie om nabijgelegen treinen op te halen. |
| Route plannen in Kaarten op iOS | De gekozen bestemming wordt doorgegeven aan Apple Kaarten. |
| Foto of ZIP delen | De door jou gekozen app, opslagdienst of ontvanger krijgt de geselecteerde bestanden en de daarin aanwezige gegevens. |

Bij netwerkverzoeken ontvangt de dienst ook je IP-adres en gebruikelijke technische verbindingsgegevens. De bewaartermijnen en verdere verwerking bij deze diensten zijn niet uit de appbroncode vast te stellen.

De gecontroleerde mobiele broncode bevat geen automatische upload van projectfoto's naar een eigen RailMapTD-server en geen advertentie- of analyse-SDK. Dat betekent niet dat alle functies offline werken: bovenstaande netwerkverzoeken blijven van toepassing.

## Locatie, camera en horloge

Locatie en kompas worden gebruikt voor spoorpositie, richting, nabijgelegen objecten en fotometadata. De camera wordt gebruikt voor foto's en het scannen van Scope-QR-overdrachten. Scope JSON en de inhoud van QR-overdrachten worden in de app verwerkt.

Op iOS kan `Live Watch updates op achtergrond` locatiegebruik op de achtergrond inschakelen en aanvullende locatietoestemming vragen. Je kunt deze functie uitschakelen bij `Watch en haptiek`. Locatietoestemming kun je ook in de systeeminstellingen wijzigen.

De gekoppelde horloge-app ontvangt veldstatus, zoals projectnaam, geocode, spoor, kilometrering, GPS-nauwkeurigheid en objectmeldingen. De Apple Watch bewaart de laatst ontvangen status lokaal en kan deze opnieuw tonen wanneer de iPhone niet bereikbaar is. Controleer het tijdstip van de update. Wear OS ontvangt status via de gekoppelde Android-telefoon.

## Bewaren, reservekopieën en verwijderen

Projectgegevens blijven lokaal beschikbaar totdat je ze verwijdert; er is geen algemene automatische vervaltermijn voor projecten. Verwijder foto's of projecten via de app wanneer je ze niet meer nodig hebt.

Op iOS maakt het herberekenen van bestaande foto's eerst een reservekopie in de projectmap. Eerdere exports en reservekopieën kunnen oudere foto's of metadata bevatten, ook nadat je een afzonderlijke foto hebt bewerkt of verwijderd. Controleer deze kopieën afzonderlijk. Het verwijderen van het project verwijdert de lokale projectmap.

Android staat systeemback-ups toe. Ook apparaat- of cloudback-ups kunnen, afhankelijk van je platform en instellingen, appgegevens bevatten. Verwijderen in RailMapTD verwijdert geen eerder gedeelde bestanden, kopieën bij ontvangers of bestaande systeemback-ups. Beheer die via de betreffende opslagdienst of systeeminstellingen. Een gecachte horlogestatus is eveneens een afzonderlijke lokale kopie.

## Zelf bepalen wat je deelt

- Schakel treinnadering uit als je hiervoor geen locatie naar NS wilt sturen.
- Gebruik achtergrondlocatie alleen wanneer je live Watch-updates nodig hebt.
- Controleer foto's, originelen en `metadata.csv` vóór delen; een ZIP kan precieze opnameposities en werkgegevens bevatten.
- Verwijder overbodige projecten, exports en reservekopieën.
- Trek camera- of locatietoestemming zo nodig in via de systeeminstellingen; bijbehorende functies kunnen dan niet volledig werken.

## Publicatie en contact

Dit document is een technische toelichting op de app en bevat nog geen vastgestelde contactgegevens van de verantwoordelijke uitgever. Voor gebruik als gepubliceerde privacyverklaring moeten de uitgever en het privacycontact worden ingevuld en moeten de feitelijke distributie, bewaartermijnen en afspraken met dienstverleners worden gecontroleerd. Deze organisatiegegevens zijn niet uit de broncode af te leiden.

Zie ook de [iOS-handleiding](../Help.md) en [Android-handleiding](RailMapTD-help.html).

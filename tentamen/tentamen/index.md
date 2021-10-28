# Tentamen

*C en Python voor Beta-gamma, 28 oktober 2021, 13:00--16:00 uur.*

Hieronder vind je vijf opdrachten van verschillende niveaus. Om het tentamen te halen moet je minimaal één goedwerkend programma van het eerste niveau inleveren en twee goedwerkende programma's van het tweede niveau.

Het doel is te demonstreren dat je zelfstandig een oplossing voor een probleem kunt ontwikkelen, en daarbij gebruik kunt maken van de basistechnieken van programmeren in C, zoals bijvoorbeeld de verschillende soorten loops, if-else-constructies, enzovoort.

Vanwege dit doel heeft het geen zin om alleen het juiste antwoord uit te printen zodat `check50` tevreden is (het zogenaamde "hardcoden"). Het is daarom ook aan te raden om zoveel mogelijk van de opdrachten te doen, mits de tijd dit toelaat. Dat geeft ruimte als je onbedoeld een antwoord hebt ge-hardcode.

De input van gebruikers hoeft alleen gecontroleerd te worden als dit duidelijk in de opdracht vermeld staat.

> Als bronnen mag je gebruiken: de lecture notes (en de rest van de website), de CS50 Manual waarin allerlei nuttige C-functies genoemd staan, en je eigen uitwerkingen van andere opdrachten. Je mag geen andere bronnen gebruiken en niet op één of andere manier met iemand anders communiceren over de opgaven tijdens het maken van het tentamen.


## Reistijd

Je maakt een reis naar het Friese platteland (of elders) en je wil vooraf de reistijd berekenen. Natuurlijk ga je dat niet éénmalig doen, maar schrijf je een programma dat de prijs altijd even voor je kan uitrekenen op basis van de af te leggen afstanden. Ook kies je of je voor het laatste stuk de OV-fiets of de bus gebruikt.

Het eerste stuk doe je met de fiets: 18 km per uur. Het tweede stuk met de trein: 70 km per uur. En het derde stuk naar keuze met de OV-fiets (16 km per uur, altijd meer wind daar) of met de bus (10 km per uur).

Schrijf het programma dat op basis van ingevoerde afstanden de totaalprijs van de reis berekent.

    $ ./reisprijs
    Afstand fietsen: 2.6
    Afstand treinen: 200
    Doe je het laatste stuk met bus of fiets? B
    Afstand: 4.2
    De reis kost je ongeveer 205 minuten.

    $ ./reisprijs
    Afstand fietsen: 5.5
    Afstand treinen: 50.5
    Doe je het laatste stuk met bus of fiets? F
    Afstand: 3
    De reis kost je ongeveer 73 minuten.

Tip: de formule voor tijd in minuten is `afstand / km_per_uur * 60`.


## Getal raden

Schrijf een programma dat je vraagt een getal te raden. Door hints te geven kom je dichterbij het juiste getal. Het programma eindigt als het juiste getal is geraden.

Het is een beetje een saaie versie van het spel, omdat het te raden getal altijd 6 is. Dit getal moet dus bovenaan je programma staan in een variabele. Als de variabele wordt aangepast moet het spel wél volgens de regels blijven werken. (We doen dit voor het automatisch checken. Later kun je het programma uitbreiden door een random getal te genereren.)

    $ ./raden
    Welk getal: 10
    -> te hoog
    Welk getal: 3
    -> te laag
    Welk getal: 6
    -> goed!
    
    $ ./raden
    Welk getal: -2
    -> te laag
    Welk getal: 10
    -> te hoog
    Welk getal: 1
    -> te laag
    Welk getal: 6
    -> goed!


## Elektrisch rijden

De aanschaf van een elektrische auto is vaak nog duurder dan een benzineauto, maar de verbruikskosten niet. De benzineprijs is inmiddels gestegen naar 1,95 euro per liter, waarmee je ongeveer 1 op 25 km rijdt. Elektrisch laden kost gemiddeld 30 cent per kilowattuur, waarbij het verbruik ongeveer 1 op 5 km is.

Voor de handigheid hier de formules:

- Het aantal gebruikte liters benzine is `aantal kilometers / 25`
- Het aantal gebruikte kilowattuur is `aantal kilometers / 5`

Schrijf een programma dat een tabel print waarin zichbaar is hoeveel goedkoper elektrisch rijden is dan de benzineauto, voor 100 t/m 900 km per maand.

    $ ./elektrisch
    Benzineprijs: 1.95
    Laadprijs: 0.3
    | KM    | Elektrisch | Benzine  |
    | 100   |  6.00      |  7.80    |
    | 200   | 12.00      | 15.60    |
    | 300   | 18.00      | 23.40    |
    | 400   | 24.00      | 31.20    |
    | 500   | 30.00      | 39.00    |
    | 600   | 36.00      | 46.80    |
    | 700   | 42.00      | 54.60    |
    | 800   | 48.00      | 62.40    |
    | 900   | 54.00      | 70.20    |

    $ ./elektrisch
    Benzineprijs: 2.1
    Laadprijs: 0.33
    | KM    | Elektrisch | Benzine  |
    | 100   |  6.60      |  8.40    |
    | 200   | 13.20      | 16.80    |
    | 300   | 19.80      | 25.20    |
    | 400   | 26.40      | 33.60    |
    | 500   | 33.00      | 42.00    |
    | 600   | 39.60      | 50.40    |
    | 700   | 46.20      | 58.80    |
    | 800   | 52.80      | 67.20    |
    | 900   | 59.40      | 75.60    |


## Huis

Schrijf een programma dat een huis uitprint. De gebruiker mag een hoogte opgeven. Deze hoogte mag niet kleiner dan 2 zijn en niet groter dan 20.

    $ ./huis
    Hoe hoog moet het zijn? 4
       x
      x x
     x   x
    x     x
    x     x
    x     x
    x     x
    xxxxxxx

    $ ./huis
    Hoe hoog moet het zijn? 2
     x
    x x
    x x
    xxx

    $ ./huis
    Hoe hoog moet het zijn? -3
    Hoe hoog moet het zijn? 40
    Hoe hoog moet het zijn? 1
    Hoe hoog moet het zijn? 5
        x
       x x
      x   x
     x     x
    x       x
    x       x
    x       x
    x       x
    x       x
    xxxxxxxxx


## Alfabet

Schrijf een programma dat van twee woorden bepaalt welke eerder in het woordenboek voorkomt. Ook maken we geen verschil tussen hoofdletters en kleine letters.

Maar begin eens bij een eenvoudiger geval:

    $ ./alfabet
    Woord 1: Taylor
    Woord 2: Lana
    Lana first

    $ ./alfabet
    Woord 1: shark
    Woord 2: sWoRd
    shark first

    $ ./alfabet
    Woord 1: Daantje
    Woord 2: Daan
    Daan first

    $ ./alfabet
    Woord 1: amanda
    Woord 2: Amanda
    No need to decide!

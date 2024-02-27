---
title: Protocol-denken
taxonomy:
  category:
    - Bliki
    - Architecture
---
Protocol-denken is ontstaan in het team <a href="https://www.kadaster.nl/zakelijk/over-ons/innovatie" target="_blank">Emerging Technology Center</a> van het <a href="https://kadaster.nl" target="_blank">Kadaster</a>.  Daarom eer en dank aan <a href="https://www.linkedin.com/in/btazrouti/" target="_blank">Badreddine Tazrouti</a>, <a href="https://www.linkedin.com/in/koenhuisstede/" target="_blank">Koen Huisstede</a> en <a href="https://www.linkedin.com/in/nickvapeldoorn/" target="_blank">Nick van Apeldoorn</a> voor de ontwikkeling van deze ideeën en het 'bestuiven' van dit concept en de ideeën! :heart:

**Protocol-denken** is een eigen term. Het is een toekomstvisie en perspectief gebaseerd op de geschiedenis en evolutie van technologie, internet en het digitale tijdperk. Als we naar deze evolutie kijken en de ontwikkeling van vandaag trachten te projecten, dan kunnen we een aantal zaken herkennen die de ontwikkeling van de toekomst gaan vormen. Daarin herkennen we ontwikkelingen die lijken op het ontstaan van het internet en het web. Destijds zijn internet protocollen ontwikkeld die 'erg dun' ontworpen zijn, terwijl de protocollen van vandaag juist 'dikke protocollen' zijn. Data staat steeds meer centraal en de herkomst en ontstaan van data wordt steeds belangrijker. De uitwisseling van data is onderdeel van de digitale samenleving. Dat gaat verder dan het verbinden van computers tot het ontstaan van het internet en bouwt daarop voort. Maar wel met uitgebreidere voorwaarden en striktere uitvoering van de regels waaronder data ontstaat en uitgewisseld wordt. Een dik protocol dus. En aangezien data uitwisseling altijd tussen meerdere partijen plaatsvindt (anders is het geen data uitwisseling :grin:) is het samen ontwikkelen van deze protocollen randvoorwaarde. Sterker nog, om vertrouwen te hebben in de data uitwisseling en de data zelf (incl. het ontstaan, herkomst, etc) is het noodzakelijk dat ook deze protocollen open zijn, zoals ook de internet procotollen open zijn. Open Source en Open Standaarden zijn hierin de manier van werken voor het ontstaan en ontwikkelen van deze protocollen. Dit is protocol-denken in het kort.

## Ontstaan van data

Een belangrijk onderdeel van het protocol-denken en ook een relevant onderwerp van vandaag, is de herkomst en het ontstaan van data. In de geschiedenis van registers, grootboeken op papier, de standaardisatie daarvan, de mechanisatie daarvan en vervolgens de automatisering daarvan, staan we op het punt om onze processen opnieuw te gaan ontwerpen voor een echte _digitalisering_. Hier moeten we bekennen dat we van mechanisatie naar automatisering vooral de papieren boeken hebben gerespecteerd en digitaal beschikbaar gemaakt. Onze boeken, registers, grootboeken hebben we in een database en bijbehorende applicatie gestopt. Da's een mooi begin ... maar we hebben een volgende stap nodig om het ontstaan van data serieus te beschrijven en digitaal beschikbaar te maken. Dit is een paradigma verschuiving, een 'paradigm shift'.

![From Single Model to Commands, Events and Queries](/_images/event-sourcing-paradigm-shift.png)

Voor het ontstaan is het architectuurpatroon [[Event Sourcing]] van groot belang. Het is niet de 'heilige graal' en de oplossing voor alles, maar het geeft antwoord op het ontstaan van data, op de evolutie van data. Het adresseert ook dat data-gebeurtenissen, oftewel events, gebeurd zijn en dat we daar 'mee moeten dealen'. Als er een fout in een register zit, kunnen we dat register vrij eenvoudig aanpassen, ook in het verleden. Met events dienen we dat expliciet te beschrijven en daarmee moeten we _ontwerpen_ hoe en dat we correcties gaan toepassen.

Een ander aspect van [[Event Sourcing]] is dat de evolutie van een register, een grootboek, beschreven in de stroom van events (data-gebeurtenissen), leidt tot een _projectie_. Ons bekende register, grootboek, boek met resultaten is een projectie van de events, welke wordt opgebouwd door alle events 'af te spelen' volgens regels. Dit maakt het mogelijk om _meerdere_ projecties te maken op basis van dezelfde stroom van events. Er is hierin zeer zeker een _primaire projectie_ wat de reden van het register of grootboek is. Tegelijk zijn er eerdere meerdere en vele projecties die secundair zijn aan de primaire reden van bestaan en zeer relevant zijn. Zeker in het geval dat de data, het register, het grootboek, ergens anders gebruikt wordt. Het is zeer waarschijnlijk dat dit gebruik van de data een aangepaste projectie nodig heeft die specifiek past bij die behorende context waarin de data gebruikt wordt.

![Multiple projections](/_images/event-sourcing-multiple-projections.png)

> Er kan veel kennis en ervaring gehaald worden uit het architectuurpatroon [[Event Sourcing]]. (Nogmaals) dit is geen 'silver bullet' en altijd en overal toe te passen. En tegelijk biedt het wel veel aanknopingspunten voor de digitale samenleving waar we naartoe werken.

## Contexten

Bij het respecteren van het [ontstaan van data](#ontstaan-van-data) moeten we ook constateren en respecteren dat data ontstaat vanuit een duidelijke **context**. De stelling is dat het ontstaan _altijd_ één context heeft, welke heel duidelijk en expliciet is. Data ontstaat _altijd_ op één plaats, één tijd door één actor. Dit is de context waarin de data ontstaat.

Daar waar de data gebruikt wordt, is steeds vaker veelzijdig en vanuit heel verschillende perspectieven. Dit duiden we aan met _gebruikscontexten_. Vanuit de _ontstaanscontext_ zijn er vaak vele _gebruikscontexten_ en elke 'overgang' dient expliciet ontworpen te worden. Hierin wordt verantwoord hoe begrippen en semantiek op elkaar aansluiten (of niet) tussen de contexten en welke transformatie(s) er nodig zijn en toegepast worden.

![Bounded Contextx](/_images/ddd-bounded-contexts.png)

Data uitwisseling vindt altijd plaats _tussen_ partijen. Er zijn dus altijde _meerdere_ partijen betrokken. Hoe die uitwisseling plaatsvindt, is daarom een afspraak tussen de partijen. Voor een ontstaanscontext is het prettiger als er een beperkt aantal context overgangen gedefinieerd zijn en geleverd worden. Dit is in het belang van de ontstaanscontext eigenaar welke ook wel bronhouder genoemd wordt. Daar ontstaat tenslotte de data. Het is daarom aan de ontstaanscontext eigenaar / bronhouder om te organiseren dat alle gebruikscontexten goed worden voorzien en geoptimaliseerd worden door uniformiteit.

> Vanuit [Domain Driven Design](https://martinfowler.com/bliki/DomainDrivenDesign.html) worden [Bounded Contexts](https://martinfowler.com/bliki/BoundedContext.html) een expliciet begrip. Dit is goede basis om dit hoofdstuk goed te doorgronden.

## Open samenwerken

Data uitwisselen is, zoals diverse keren aangestipt, een kwestie van meerdere organisaties. Om de overgang tussen [contexten](#contexten) goed te faciliteren, dienen deze partijen samen te werken. Dat werkt het gemakkelijkste en op de beste manier als dat een open samenwerking is. Dat draagt niet alleen bij aan een betere uitvoering van de data uitwisseling, maar ook een hogere betrouwbaarheid daarvan. Bovendien is er geen enkele partij die macht kan opbouwen en/of gebruiken om de data uitwisseling extreem te beinvloeden. Dit voorkomt een lock-in van elke kant.

Er is al jaren ervaring in het ontwikkelen van open standaarden en open source software. Gebruiken, ervaringen en organisatie kan hier van afgekeken worden. Vooral open source wordt nog te weinig toegepast en begrepen. Hoewel open source vooral op open source software lijkt te duiden, is het nog veel meer een open samenwerkingsmodel dan dat het echt software betreft. Het is meer _open source werken_ dan open source software.

Een voordeel van open source werken én tegelijk dat realiseren in open source software is dat er een werkend product is van de afspraken. Het toont aan dat het niet alleen een afspraak en beschreven contract is, maar dat er een uitvoerbaar contract is: [strikte en uitvoerbare contracten](#strikte-en-uitvoerbare-contracten).

## Strikte en uitvoerbare contracten

Het concept van 'dikke protocollen' komt uit de [[Blockchain]] hoek. Nee, niet direct afhaken! Protocol-denken is niet een blockchain of [[Distributed Ledger Technology]]. Wat daar wel vandaan komt, is het concept van _Smart Contracts_. Een uitvoerbare en strikte afspraak die in code is vastgelegd. Er is voor alle partijen geen twijfel dat er aan de afspraak voldaan wordt, want er is de garantie dat een computer het gaat uitvoeren en de code beschrijft volledig en expliciet wat er dan uitgevoerd gaat worden.

De data uitwisseling en de overgang van [[contexten]] kan op dezelfde manier beschreven worden in uitvoerbare contracten. Dit maakt strikte contracten waarover geen twijfel bestaat en welke vertrouwen bieden aan de uitvoering, het gebruik en de voorwaarden. Deze zijn allemaal expliciet en volledig machine-leesbaar beschreven en worden uitgevoerd, bijvoorbeeld ten tijde van de data uitwisseling.

---
layout: post
title: Hoe kan ik met Tomahawk bewoner-eigenaren vinden die in aanmerking komen voor de SPUK LAI regeling?
categories: [Achtergrond, Spuklai]
excerpt: Met de Specifieke Uitkering (SPUK) Lokale Aanpak Isolatie (LAI) zetten gemeenten een eigen isolatieprogramma op voor inwoners met een slecht geïsoleerde koopwoning. In dit artikel vind je hoe deze dataset tot stand is gekomen en hoe je deze vervolgens eenvoudig kunt inzetten in je organisatie.
---

Met de Specifieke Uitkering (SPUK) Lokale Aanpak Isolatie (LAI) zetten gemeenten een eigen isolatieprogramma op voor inwoners met een slecht geïsoleerde koopwoning. Daarmee bieden gemeenten ondersteuning aan (verenigingen van) eigenaren die moeite hebben hun woning te verduurzamen. 

Eigenaren moeten voldoen aan een aantal criteria om in aanmerking te komen voor de SPUK LAI subsidies bij het toepassen van isolatiemaatregelen. Om gemeenten te helpen de gebouwen en addressen te vinden van inwoners die voldoen aan deze criteria, heeft Tomahawk de SPUK LAI Doelgroep dataset ontwikkeld.

In dit artikel vind je hoe deze dataset tot stand is gekomen en hoe je deze vervolgens eenvoudig kunt inzetten in je organisatie:

* [Totstandkoming van de dataset](#Totstandkoming-van-de-dataset)
* [Visualisatie van de SPUK LAI doelgroep](#Visualisatie-van-de-SPUK-LAI-doelgroep)
* [Exporteren van SPUK LAI doelgroep adressen exporteren naar Excel](#Exporteren-van-SPUK-LAI-doelgroep-adressen-exporteren-naar-Excel).

## Totstandkoming van de dataset
Er zijn vier criteria die bepalen of een adres in aanmerking komt voor SPUK LAI subsidie:

- **Gebouwtype**: Het betreft een woning
- **Eigendom**: De bewoner en eigenaar zijn eendezelfde persoon ('bewoner-eigenaar').
- **Woningwaarde**: De woning heeft een WOZ waarde die gelijk of lager ligt dan het gemeentelijke gemiddelde in 2022 zoals gepubliceerd in de Staatscourant.
- **Isolatieniveau**: De woning heeft een energielabel D of slechter, of heeft tenminste twee ongeisoleerde bouwdelen.

Om de SPUK LAI dataset te genereren is in Tomahawk elk van deze criteria bepaald en vervolgens gecombineerd.

##### Gebouwtype

Tomahawk beschikt over data uit de Basisadministratie Gebouwen (BAG) waarin staat wat de gebruiksfunctie is van een gebouw/adres. Hiermee worden gebouwen zonder woonfunctie uitgesloten.

##### Eigendom
Uit een dataset van het Planbureau van de Leefomgeving (PBL) is indicatief bepaald of een gebouw in privaat eigendom is, commercieel wordt verhuurd of in eigendom van een woningcorporatie is. In gestapelde bouw kunnen meerdere vormen voorkomen. Er wordt dan gesproken over gespikkeld bezit.

Gebouwen die in privaat eigendom zijn, voldoen aan het criterium van SPUK LAI, gebouwen die behoren tot een woningcorporatie voldoen niet aan het criterium. De dataset van PBL bevat enige onzekerheden, waardoor Tomahawk niet accuraat kan aangeven of een woning daadwerkelijk commercieel wordt verhuurd en of er in gespikkelde bezit gebouwen ook bewoner-eigenaren zijn. Deze vormen van eigendom worden daarom aangemerkt als 'onzeker' of zij voldoen aan het SPUK LAI criterium.

##### Woningwaarde
Tomahawk beschikt over de WOZ waarde in 2022 per postcode6 gebied, zoals samengesteld door het CBS. Deze dataset is per gebouw gecorrigeerd op basis van het vloeroppervlak, om zo een nauwkeuriger inschatting te krijgen van de WOZ-waarde.

In de Staatscourant is voor de SPUK LAI regeling voor elke gemeente gepubliceerd wat de gemiddelde WOZ-waarde treshold is per gemeente. Deze thresholds zijn ingevoerd in Tomahawk en tegen de ingeschatte WOZ-waarde van het CBS gelegd. Een gebouw voldoet aan het criterium als deze een WOZ waarde heeft die kleiner of gelijk is dan de threshold.

##### Isolatieniveau
Ongeveer 25% van alle gebouwen in Nederland heeft een energielabel. Hiervoor kan eenvoudig worden vastgesteld of deze wel of niet voldoen aan het SPUK LAI criterium.

Voor de overige 75% van de gebouwen geldt het criterium van minimaal twee niet-geisoleerde bouwelementen. Tomahawk beschikt niet over deze data.

Om toch een inschatting te kunnen maken voor deze gebouwen is er een indicatief label berekend. Per postcode6 gebied is voor elk gebouw het label bepaald aan de hand van de gebouwen met energielabel in hetzelfde postcode gebied. Een gewogen gemiddelde is toegepast op basis van de afstand tussen de gebouwen. Daardoor weegt een energielabel van de naaste buur zwaarder mee dan die van een gebouw een straat verder op.

De indicatieve energielabels zijn ook als losse kaartlaag in te zien.

##### SPUK LAI doelgroep
De SPUK LAI doelgroep zijn de gebouwen die voldoen aan de SPUK LAI criteria. De volgende uitkomsten zijn mogelijk

* Het gebouw voldoet aan alle vier de criteria en krijgt het label _Ja_
* Het gebouw is een woning, heeft een private eigenaar, een ondergemiddelde WOZ waarde en een indicatieve label C. Deze gebouwen worden als _Onzeker_ gelabeld, omdat er enige onzekerheid zit in de bepaling van het indicatieve label.
* Het gebouw is een woning, heeft een ondergemiddelde WOZ waarde en een (indicatieve) label D, E, F of G, maar eigendom is commerciele verhuur of gespikkeld bezit. Deze gebouwen worden als _Onzeker_ gelabeled.
* Alle andere gebouwen zijn als _Nee_ gelabeld.

## Visualisatie van de SPUK LAI doelgroep
Met de volgende stappen bekijk je alle woningen in je gemeente die voldoen aan de SPUK LAI doelgroep criteria op een interactieve kaart. 

* Open de (Tomahawk applicatie)[https://app.tomahawk-energy.nl]
* Ga naar _Kaart_
* Selecteer onder _kaartlagen_ de laag _SPUK LAI Doelgroep_.
* De kaart kan ongeveer 20.000 gebouwen tegelijkertijd weergeven. Zie je niets verschijnen? Zoom dan verder in op de kaart.

![](/images/20240913-05.jpg)

## Exporteren van SPUK LAI doelgroep adressen exporteren naar Excel
Met de volgende stappen exporteer je alle woningen in je gemeente die voldoen aan de SPUK LAI doelgroep criteria naar Excel.

* Open de (Tomahawk applicatie)[https://app.tomahawk-energy.nl]
* Ga naar _Mijn projecten_
* Kies _Nieuw project_
* Geef het project een naam en eventueel een omschrijving

![](/images/20240913-01.png)

* Ga naar de kaart.
* Type in het veld _zoeken naar gebied_ de naam van de gemeente in waarvoor je een export maakt. Je kunt eventueel ook zoeken naar een wijk of buurt.
* Kies de gemeente uit de dropdown menu
* Kies _selecteren_
* Kies _opslaan_

![](/images/20240913-02.jpg)

* Ga naar _filters_
* Selecter in de SPUK LAI doelgroep het veld _ja_. Als je ook de woningen wilt exporteren waarvan niet met zekerheid is te zeggen of zij voldoen, selecteer dan ook het veld _onzeker_
* Druk op _opslaan_

* Ga vervolgens naar _analyse_
* Ga naar _export_
* Kies _adressen_
* In het bestandsformaat kies voor Excel.
* Selecteer eventueel het vakje SPUK LAI om de achtergronddata te verkrijgen
* Druk op _exporteren_

![](/images/20240913-03.png)

Na zo'n 30 tot 60 seconden zal het Excel bestand worden gedownload.

![](/images/20240913-04.png)

Gebruik de Excel sheet om bijvoorbeeld een mailing uit te sturen naar je inwoners.
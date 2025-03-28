---
layout: post
title: Wat is een discontovoet en welke impact heeft deze op een business case van een warmtebedrijf?
categories: [Achtergrond, Business case]
excerpt: Met Tomahawk 4.0 kun je een business case voor een warmtebedrijf berekenen. Een belangrijke, en vaak onbegrepen parameter hierin is de discontovoet. In dit artikel leggen we uit wat dit is en hoe het werkt.

---

Met Tomahawk 4.0 kun je een business case voor een warmtebedrijf berekenen. Een belangrijke, en vaak onbegrepen parameter hierin is de discontovoet. In dit artikel leggen we uit wat dit is en hoe het werkt.


In dit artikel:

* [[Hoe stel je een business case voor een warmtebedrijf op?](#X6a4fb16d54a5bd361f43fd1aae38b86f82c14d5)](#[Hoe stel je een business case voor een warmtebedrijf op?](#X6a4fb16d54a5bd361f43fd1aae38b86f82c14d5))
* [Bepaling van de bijdrage aansluitkosten (BAK)](#Bepaling van de bijdrage aansluitkosten (BAK))
* [Discontovoet](#Discontovoet)
* [Effect van discontovoet op de BAK](#Effect van discontovoet op de BAK)

## [Hoe stel je een business case voor een warmtebedrijf op?](#X6a4fb16d54a5bd361f43fd1aae38b86f82c14d5)

Een business case bereken je over een vooraf bepaalde periode, meestal 30 jaar.  , De periode kun je ook aanpassen in de _Instellingen_ onder _Scenario studie_. Voor elk jaar binnen deze periode bereken je de kosten en opbrengsten apart.

### Voorbeeld:

We nemen als voorbeeld een installatie binnen een warmtenet met de volgende kenmerken:

* **Investeringskosten**: 100 euro
* **Levensduur**: 10 jaar
* **Onderhoudskosten**: 1% van de investeringskosten per jaar (1 euro)

Om het voorbeeld eenvoudig te houden, laten we inflatie buiten beschouwing.

### Berekening:

* **Jaar 0**: initiele investering van 100 euro.
* **Jaar 10**: vervanging van de installatie,  100 euro investeren.
* **Jaar 20**: nogmaals vervanging van de installatie, 100 euro investeren
* **Elk jaar**: onderhoudskosten van 1% (1 euro)

### Overzicht in tabelvorm:

De tabel toont de jaren binnen de business case-periode. Per jaar zijn de investeringen, onderhoudskosten en totale kosten weergegeven volgens bovenstaande gegevens.

```
Jaar             0      1      2      3      4 .... 9     10     11 ... 19     20     21 ... 29     30 
-----------------------------------------------------------------------------------_**-------------------
Investering    100                                       100                  100**_
Onderhoud        1      1      1      1      1      1      1      1      1      1      1      1      1

======================================================================================================
TOTAAL KOSTEN  101      1      1      1      1      1    101      1      1    101      1      1      1
```

Stel dat er jaarlijks 9 euro aan inkomsten is. Dan bereken je het resultaat door de kosten van de inkomsten af te trekken (inkomsten - kosten). Als het resultaat positief is, spreken we van winst. Is het resultaat negatief, dan betekent dit een verlies voor dat jaar.

```
Jaar             0      1      2      3      4 .... 9     10     11 ... 19     20     21 ... 29     30 
------------------------------------------------------------------------------------------------------
Inkomsten        9      9      9      9      9      9      9      9      9      9      9      9      9
Uitgaven       101      1      1      1      1      1    101      1      1    101      1      1      1

======================================================================================================
Resultaat      -92      8      8      8      8      8    -92      8      8    -92      8      8      8          
```
## Bepaling van de bijdrage aansluitkosten (BAK)

Om een negatieve business case sluitend te maken, vraag je een bijdrage aansluitkosten (BAK) van klanten. Dit bedrag moet minimaal gelijk zijn aan het negatieve resultaat. In dit voorbeeld leidt dit tot een totaalresultaat van **-60 euro**. Dit negatieve resultaat betekent dat er gedurende de looptijd meer uitgaven zijn dan inkomsten, waardoor de business case niet sluitend is.

Bij warmtenetten is dit een veelvoorkomende situatie. Om de business case sluitend te maken, vraagt het warmtebedrijf  van (toekomstige) klanten een aansluitingvergoeding, de zogenaamde **bijdrage aansluitkosten (BAK)**. Het totaal van alle BAK-bijdragen moet minimaal gelijk zijn aan het negatieve resultaat (in dit geval **60 euro**) om de business case sluitend te maken. 

Voegen we deze BAK namelijk toe aan bovenstaande voorbeeld, dan is de som van het resultaat precies 0.
```
Jaar             0      1      2      3      4 .... 9     10     11 ... 19     20     21 ... 29     30 
------------------------------------------------------------------------------------------------------
BAK				60
Inkomsten        9      9      9      9      9      9      9      9      9      9      9      9      9
Uitgaven       101      1      1      1      1      1    101      1      1    101      1      1      1

======================================================================================================
Resultaat      -32      8      8      8      8      8    -92      8      8    -92      8      8      8         
```

## Discontovoet

Een belangrijke parameter  ontbreekt nog in deze business case is de discontovoet. De discontovoet houdt rekening met de waarde van geld over tijd. Bijvoorbeeld, bij een discontovoet van 5% is 100 euro over vijf jaar vandaag ongeveer 78 euro waard

Factoren die de discontovoet (waarde verlaging) beïnvloeden:

* **Inflatie**:  Door een hogere inflatie daalt de waarde van geld. Daardoor stijgt de  discontovoet. 
* **Risico**: Projecten of investeringen met meer onzekerheden krijgen een hogere discontovoet om het hogere risico te compenseren.
* **Rentepercentages**: Centrale banken stellen rentetarieven vast, en deze hebben direct invloed op de kosten van kapitaal en dus op de discontovoet.
* **Economische groei**: In een snelgroeiende economie kan de discontovoet hoger zijn, omdat er betere alternatieve investeringsmogelijkheden zijn met hogere rendementen.
* **Verwacht rendement**: Als beleggers een hoog rendement eisen (bijvoorbeeld door marktconcurrentie), stijgt de discontovoet.
* **Marktomstandigheden**: Economische onzekerheden, zoals recessies of geopolitieke spanningen beïnvloeden
 de discontovoet.
* **Looptijd van het project**: Hoe langer de looptijd, hoe groter de onzekerheid en de kans op een hogere discontovoet.
* **Sector-specifieke factoren**: Bijvoorbeeld: discontovoeten in technologie zijn vaak hoger door snelle veranderingen en innovatie, terwijl discontovoeten in infrastructuurprojecten lager kunnen zijn door stabiliteit.

Voor warmte(koude)bedrijven liggen discontovoeten meestal tussen **6% en 9%**.

### Contante waarde en netto contante waarde

Een resultaat waarop een discontovoet is toegepast, heet een **contante waarde**. 

In het eerdere voorbeeld passen we nu een discontovoet van **6%** toe en berekenen we de contante waarde voor elk jaar. Zoals te zien is, daalt de contante waarde naarmate het resultaat verder in de toekomst ligt. Dit laat zien dat de waarde van geld afneemt over tijd.

```
Jaar                 0      1      2      3      4 .... 9     10     11 ... 19     20     21 ... 29     30 
------------------------------------------------------------------------------------------------------
Inkomsten            9      9      9      9      9      9      9      9      9      9      9      9      9
Uitgaven           101      1      1      1      1      1    101      1      1    101      1      1      1

======================================================================================================
Resultaat          -92      8      8      8      8      8    -92      8      8    -92      8      8      8 
Contante waarde    -92.0    7.5    7.1    6.7    6.3    4.7  -51.4    4.2    2.6  -28.7    2.4    1.6    1.5       
```

Een business case is haalbaar al de som van de contante waardes gelijk of groter is dan 0. Deze som heet de **netto contante waarde** (NCW). Voor dit specifieke voorbeeld bedraagt de netto contante waarde **-70,3 euro**. Dit negatieve resultaat betekent dat de totale kosten hoger zijn dan de inkomsten. Om een sluitende business case te realiseren, is een totale bijdrage aansluitkosten (BAK) van **70,3 euro** nodig.

## Effect van discontovoet op de BAK

De hoogte van de discontovoet beïnvloed de netto contante waarde (NCW), omdat deze bepaalt hoeveel toekomstige inkomsten en uitgaven vandaag waard zijn. Dit heet verdisconteren. Je bepaalt vandaag wat je moet inzetten/inleggen om een bepaald bedrag te ontvangen in de toekomst Bij een hogere discontovoet neemt de huidige waarde van inkomsten en uitgaven verder in de toekomst af, omdat de factor waarmee wordt verdisconteerd groter is.

In onderstaande tabel zijn de contante waarden berekend bij een discontovoet van 6% en 12%. De netto contante waarde komt in deze voorbeelden uit op respectievelijk **-70,3 euro** en **-70,4 euro**.

```
Jaar                       0      1      2      3      4 .... 9     10     11 ... 19     20     21 ... 29     30 
Resultaat                -92      8      8      8      8      8    -92      8      8    -92      8      8      8 
Contante waarde ( 6%)    -92.0    7.5    7.1    6.7    6.3    4.7  -51.4    4.2    2.6  -28.7    2.4    1.6    1.5
Contante waarde (12%)    -92.0    7.1    6.4    5.7    5.1    2.9  -29.6    2.3    0.9   -9.5    0.7    0.3    0.3
```

In dit geval heeft de discontovoet dus slechts een klein effect op de netto contante waarde. Het precieze effect van een hogere discontovoet hangt af van de verhouding tussen lopende kosten, herinvesteringskosten en inkomsten. De netto contante waarde kan hierdoor hoger, gelijk of lager uitvallen, wat niet altijd direct intuïtief is.
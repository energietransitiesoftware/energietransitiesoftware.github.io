---
layout: post
title: Gelijktijdigheidsfactoren in warmtenetten
categories: [Achtergrond, Warmtenetten]
excerpt: Gelijktijdigheidsfactoren in warmtenetten — waar komen ze vandaan, en wat hanteert Tomahawk?
---
# Gelijktijdigheidsfactoren in warmtenetten — waar komen ze vandaan, en wat hanteert Tomahawk?

## Inleiding
Bij het ontwerpen van warmtenetten is de *gelijktijdigheidsfactor*  een cruciale parameter. De factor bepaalt hoeveel van de theoretische som van alle individuele vermogens werkelijk gelijktijdig wordt gevraagd.

Omdat niet ieder huishouden op exact hetzelfde moment verwarmt of warm tapwater gebruikt, wordt het (warmte)net nooit volledig belast. Door een gelijktijdigheidsfactor toe te passen, kan de dimensionering van bronnen, leidingen en pompen realistischer — en economischer — worden uitgevoerd.

Dit artikel legt uit hoe de gelijktijdigheidsfactoren in Tomahawk tot  stand zijn gekomen.

---

## 🌡️ Ruimteverwarming

Voor ruimteverwarming is de gelijktijdigheid relatief hoog: tijdens koude pieken verwarmen de meeste gebouwen tegelijk.
De Deense literatuur, waaronder Tol & Svendsen (DTU, 2013) en diverse praktijkmetingen in lage-temperatuur-warmtenetten, laat zien dat de gelijktijdigheidsfactor bij grotere aantallen (> 100 gebouwen) aansluitingen stabiliseert rond **0,62**.

Ook de Britse CIBSE CP1 – Heat Networks: Code of Practice hanteert vrijwel dezelfde vuistregel waarbij `N` het aantal woningen is. Bij grotere aantallen woningen resulteert dit eveneens in circa **0,62**.
```
f_SH = 0.62 + (0.38 / N)
```

In andere literatuur / referenties zoals NPro.Energy wordt vaak een gelijktijdigheid in de orde van **0,5 tot 0,8** gehanteerd, afhankelijk van schaal, gebouwtype en gebruikspatronen. Hoe kleiner de schaal, hoe hoger de gelijktijdigheidsfactor.

In Nederland worden in ISSO-publicatie 7 en de Startanalyse (PBL, 2022) **0,55** genoemd als gelijktijdigheidsfactor.  Voor utiliteit begint de gelijktijdigheid bij 70% en neemt toe bij kleiner aantal utiliteistgebouwen.

De Deense waarden zijn gebaseerd op gemeten verbruiksdata van bestaande warmtenetten en worden daarom als representatiever beschouwd voor de praktijk. Daarnaast rekent tomahawk zowel woningen als utiliteit door, waardoor het gemiddelde iets hoger komt te liggen dan alleen voor woningen.

**Tomahawk** hanteert voor ruimteverwarming op basis van literatuur een **gelijktijdigheidsfactor van 0,62**.

---

## 🚿 Tapwater

Voor tapwater is de situatie omgekeerd: de piekvraag is kort en sterk geconcentreerd (douchen, afwassen). Internationale en vooral Deense normen (DS 439 / DS 452), die gebaseerd zijn op gemeten data in reële warmtenetten, geven bij 100 woningen een gelijktijdigheidsfactor van ongeveer 10 %.

Deze waarde wordt ook gehanteerd door Nederlandse adviesbureaus zoals Merosch en Greenvis, én in de Startanalyse (CE Delft, 2022).

Het betreft hier directe levering van warm tapwater met een minimale temperatuur van 70 °C.  

**Tomahawk** hanteert op basis van deze gegevens voor warmtenetten met **aanvoertemperaturen vanaf  70 °C** een **tapwater-gelijktijdigheidsfactor van 0,10**.

---

## 💧 Tapwater met buffering en boosters

In lage-temperatuur-warmtenetten (≤ 55 °C) wordt tapwater vaak via een boosterwarmtepomp in de woning bereid, met een klein buffervat of een gelijkwaardige techniek. De aanwezigheid van de buffer verlaagt het afgenomen vermogen uit het warmtenet (typisch 2 kW i.p.v. 21 kW voor direct douchen) en daalt de piekbelasting per woning met ongeveer **90 %**. Echter, de boosters draaien langer waardoor de gelijktijdigheid stijgt.

Op basis van het rekenmodel kan een inschatting gemaakt worden van de gelijktijdigheid bij aanwezigheid van een buffer.
```
f_booster ≈ (s · α / W) × (P_inst / P_boost) × (t_douche / 60)
```
waarbij:

* s = aantal douches per woning per dag
* α = fractie douches binnen het piekvenster
* W = duur van het piekvenster (uur)
* Pinst​ = thermisch vermogen tijdens douchen (kW)
* Pboost​ = thermisch vermogen boosterwarmtepomp (kW)
* tdouche​ = gemiddelde douchetijd (minuten)

Daarbij geven de termen (s⋅α/W) de **frequentie van douches** in het piekvenster en (Pinst​/Pboost​)⋅(tdouche​/60) de **duur van naverwarming** per douche aan.

Met CBS-gegevens uit 2024 (6 douches/week, 7,2 min, 2,1 bewoners/woning) en aannames van 2,5–3 u piekvenster en 50% aandeel in het piekvenster, komt de gelijktijdigheidsfactor uit op **0,36–0,43**.

Deze range wordt bevestigd door eenvoudige Monte-Carlo-schattingen: langere looptijden verhogen overlap, maar grotere spreiding verlaagt die weer.

**Tomahawk** hanteert voor **warmtenetten ≤ 55 °C** een **tapwater-gelijktijdigheidsfactor van 0,40**.

---

## ❄️ Koeling

Voor koelnetten (chilled-water-systemen, stadskoeling) is minder literatuur beschikbaar, maar internationale richtlijnen en praktijkervaringen (ASHRAE, CIBSE, LBNL, HVAC-blogs en ontwerpfora) geven een duidelijk beeld:

| Schaal / toepassing | Typische diversiteitsfactor (block-load) |
|----------------------|-------------------------------------------|
| Kleine gebouwen of zones | 0.8–0.9 |
| Meerdere gebouwen / campus | 0.7–0.8 |
| Grote stadsnetten of gemengde functies | 0.6–0.7 |

De spreiding in piekmomenten over de dag en verschillen in gebouwfunctie verlagen de gelijktijdigheid.

**Tomahawk** hanteert voor koeling een **gelijktijdigheidsfactor van 0,70**, in lijn met de internationale bandbreedte van 0,6–0,8.

---

## 📊 Samenvatting: gehanteerde waarden in Tomahawk

| Toepassing | Temperatuurregime | Gelijktijdigheidsfactor | Herkomst / motivatie |
|-------------|------------------|--------------------------|----------------------|
| **Ruimteverwarming** | ≥ 55 °C | **0.62** | Deense praktijkstudies (Tol & Svendsen), CIBSE CP1; representatief voor werkelijke netten |
| **Tapwater** | ≥ 70 °C | **0.10** | DS 439, Merosch, Greenvis, Startanalyse (PBL 2022) |
| **Tapwater** | ≤ 55 °C (met booster + buffer) | **0.40** | Afgeleid uit CBS‑gedrag en rekenmodellen; plausibel voor niet‑gespreide aansturing |
| **Koeling** | n.v.t. | **0.70** | HVAC‑ontwerppraktijk; overeenkomend met internationale range 0.6–0.8 |

---

## Gelijktijdigheid van thermische netten aanpassen in Tomahawk
De gelijktijdigheidsfactoren zijn gedefinieerd in de afleverset van de thermische netten.

- Ga naar Scenario *Studie* -> *Scenarios*
- Klik op de pen van een scenario om deze te wijzigen
- Scroll naar beneden en klik bij *Thermisch netwerk* op *Uitgangspunten wijzigen*
- Klik bij *Afleverset* op *Uitgangspunten wijzigen*
- Voer **in procenten** de gelijktijdigheidsfactoren in
    - Gelijktijdigheid van verwarmingsinstallaties (procent)
    - Gelijktijdigheid van tapwaterinstallaties (procent)
    - Gelijktijdigheid van koelinstallaties (procent)
- Druk op de knop *Opslaan*

## 📚 Bronnen en referenties

- Tol, H., & Svendsen, S. (2013). *Design of low‑energy district heating system for a settlement with low‑energy buildings*. Technical University of Denmark.
  [https://orbit.dtu.dk/en/publications/design-of-low-energy-district-heating-system-for-a-settlement-with-low-energy-buildings](https://orbit.dtu.dk/en/publications/design-of-low-energy-district-heating-system-for-a-settlement-with-low-energy-buildings)

- CIBSE (2020). *CP1 – Heat Networks: Code of Practice for the UK*. Chartered Institution of Building Services Engineers.
  [https://www.cibse.org](https://www.cibse.org)

- CE Delft (2022). *Startanalyse Aardgasvrije Wijken – PBL Rapport 2022.*
  [https://cedelft.eu/publicaties/startanalyse-aardgasvrije-wijken](https://cedelft.eu/publicaties/startanalyse-aardgasvrije-wijken)

- ISSO (2021). *Handleiding Ontwerp Warmtenetten (ISSO‑publicatie 82.1).* ISSO, Rotterdam.
  [https://www.isso.nl](https://www.isso.nl)

- DS 439 / DS 452 (Deense Normen voor Drinkwater‑ en Warmtapwaterinstallaties). Danish Standards Association.
  [https://www.ds.dk](https://www.ds.dk)

- Merosch Adviseurs (2023). *Warmtenetontwerp en Dimensionering – Praktijkrapport.*
  [https://www.merosch.nl](https://www.merosch.nl)

- Greenvis Adviseurs (2023). *Warmte‑ en koude‑infrastructuur – Referentiewaarden en Ontwerpuitgangspunten.*
  [https://www.greenvis.nl](https://www.greenvis.nl)

- ACHR News (2021). *Chilled Water Cooling Load Diversity.*
  [https://www.achrnews.com/articles/163451-chilled-water-cooling-load-diversity](https://www.achrnews.com/articles/163451-chilled-water-cooling-load-diversity)

- JMP Co Blog (2020). *Hydronic Balancing – Making the Most of System Diversity.*
  [https://jmpcoblog.com/hvac-blog/hydronic-balancing-part-2-making-the-most-of-system-diversity](https://jmpcoblog.com/hvac-blog/hydronic-balancing-part-2-making-the-most-of-system-diversity)

- LBNL / Energy Design Resources (2003). *Chilled Water Plant Design Guidelines.*
  [https://datacenters.lbl.gov/sites/default/files/EDR_DesignGuidelines_CoolToolsChilledWater.pdf](https://datacenters.lbl.gov/sites/default/files/EDR_DesignGuidelines_CoolToolsChilledWater.pdf)

- NPro.Energy
  [https://www.npro.energy/main/en/district-heating-cooling/diversity-factor?utm_source=chatgpt.com](https://www.npro.energy/main/en/district-heating-cooling/diversity-factor?utm_source=chatgpt.com)

# GeoJSON-import in Tomahawk

Met de GeoJSON-importfunctie kun je projectgebieden rechtstreeks laden vanuit GIS-software (QGIS, ArcGIS, etc.). Tomahawk ondersteunt zowel één gebied als meerdere gebieden in één bestand.

Deze documentatie beschrijft:

- welke GeoJSON-formaten worden ondersteund
- hoe de bestanden geimporteerd worden

## Ondersteunde GeoJSON-formaten

Tomahawk ondersteunt uitsluitend polygonale data, omdat projectgebieden polygonen zijn.

### Ondersteund

| Type | Ondersteuning | Toelichting |
|------|---------------|-------------|
| **Feature** | ✔ | Bevat precies één gebied |
| **FeatureCollection** | ✔ | Bevat meerdere gebieden |
| **Polygon** | ✔ | Wordt intern als MultiPolygon opgeslagen |
| **MultiPolygon** | ✔ | Direct ondersteund |

### Niet ondersteund

- Point / MultiPoint
- LineString / MultiLineString
- GeometryCollection
- FeatureCollection zonder geometry
- FeatureCollection met niet-polygon geometrie
- FeatureCollection zonder `properties.name` indien je meerdere projecten wilt laten maken

### Coördinatenstelsel
Tomahawk verwacht GeoJSON in **WGS84 (EPSG:4326)**.

Er vindt **geen reprojection** plaats.
Exporteer in je GIS-systeem dus expliciet naar WGS84 als je met RD New of andere CRS’n werkt.

### Structuurvoorbeelden

#### Eén gebied (Feature)
```json
{
  "type": "Feature",
  "properties": {},
  "geometry": {
    "type": "Polygon",
    "coordinates": []
  }
}
```

#### Meerdere gebieden (FeatureCollection)
```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": { "name": "Gebied A" },
      "geometry": {
        "type": "Polygon",
        "coordinates": []
      }
    }
  ]
}
```

De (geo)json moet opgeslagen worden in een bestand met de extensie `.json` of `.geojson`


## Importeren in Tomahawk

Er zijn **altijd drie mogelijkheden**, afhankelijk van je GeoJSON-type.

### Feature → één project met één onderzoeksgebied

Wanneer het GeoJSON-bestand één enkele **Feature** bevat:

- Tomahawk maakt **altijd één project aan**
- Het polygon- of multipolygongebied wordt opgeslagen als het **enige onderzoeksgebied** van dat project
- Er worden geen clusters gemaakt
- Tijdens het importeren geef je het project een naam.

**Gebruik wanneer:**
Je één gebied wilt analyseren, zoals één wijk, één buurtschap of één projectlocatie.

### FeatureCollection → één project met meerdere clusters

Elke Feature binnen de FeatureCollection wordt:

- een **cluster** binnen **één project**
- voorzien van een automatische kleur
- indien aanwezig: krijgt de naam van `properties.name`
- geometrieën worden **gecombineerd** tot één overkoepelend onderzoeksgebied
- Tijdens het importeren geef je het project een naam.

Het overkoepelende onderzoeksgebied = **de union van alle features**.

**Gebruik wanneer:**
- je één project wilt met subgebieden (bijv. meerdere buurten in één wijk)
- je per deelgebied analyzes wilt uitvoeren
- je per deelgebeed renovaties wilt toekennen in scenario's.

### FeatureCollection → meerdere projecten

Elke Feature wordt:

- een **los project**, met
- één onderzoeksgebied per project (geometry van die feature),
- een projectnaam afkomstig uit `properties.name`

**Belangrijk:**
Voor deze importmethode moet elke Feature een `properties.name` bevatten.

**Gebruik wanneer:**
- je per gebied een apart project wilt (bijv. alle buurten apart analyseren)
- je batch-imports wilt maken op basis van GIS-data

### Workflow

Je hebt alleen een GeoJSON-bestand nodig.

1. Ga naar **Importeer gebied (GeoJSON)** op het dashboard.
2. Upload het .geojson- of .json-bestand.
3. Tomahawk valideert het bestand.
4. Bij een FeatureCollection kies je een importstrategie:
   - één project met clusters
   - meerdere projecten
5. Kies optioneel een templateproject. De instellingen en scenario's van dit template project worden gekopieerd naar het(de) nieuwe project(en).
6. Kies of het (de) project(en) worden gedeeld met de organisatie.
7. Tomahawk maakt het project of de projecten aan.
---
layout: simple
title: Importer auf lucascranach.org
subtitle: 28.03.2024
date: 2024-03-28T08:42:36.136Z
---
Der Importer läuft nun auf dem Server (lucascranach.org). Hier liegt er unter `/var/www/shared/importer`. Bitte wenn möglich hier verwenden und nicht mehr lokal. Die XML Exporte müssen wir gewohnt ins Unterverzeichnis `input` gelegt werden. Hier dann in einen Unterordner mit dem entsprechenden Datum, z.B.:

```
/var/www/shared/importer/input/20240227
```

Die importierten Daten werden dann als JSON Dateien ins Unterverzeichnis `docs` gelegt. Hier auch in einen Ordner mit ensprechendem Datum, z.B.:

```
/var/www/shared/importer/docs/20240227
```

Hier greift der Datenendpunkt auch die Daten ab und nimmt sich immer den letzten Import. Der Aufruf sieht wie folgt aus:

```
https://lucascranach.org/data-proxy/json-data.php?type=archivals&lang=de
```

Folgende Typen stehen zur Auswahl:
- archivals
- graphics-real
- graphics-virtual
- literature
- paintings
- thesaurus

Folgender Key muss als X-API-Key im Header übergeben werden.
```
UgBtfP98rU
```

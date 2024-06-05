---
layout: simple
title: Data Proxy für neuen Metadata Service
subtitle: 05.06.2024
date: 05.06.2024
---
Ich habe gerade den image-data Proxy für den neuen Metadaten Service angepasst. Folgendes wurde gemacht:
- aufgeräumt und alte Daten in Sciebo (archiv) geschoben
- MySQL Anbindung zurück gebaut
- Pfade zu neuem Metadaten Verzeichnis gelegt
- Repo für alle Data-Proxy Dateien angelegt

```
Repo: https://github.com/lucascranach/data-proxy  
Url: https://lucascranach.org/data-proxy/image-data.php  
Params: obj=[Inventar-Nummer]_[FR-Nummer]  
Beispiel: obj=CH_SORW_1925-1b_FR006   
```

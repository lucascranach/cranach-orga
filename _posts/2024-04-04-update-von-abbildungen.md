---
layout: simple
title: Update von Abbildungen
subtitle: 04.04.2024
date: 04.04.2024
---
Etwa vier mal im Jahr kommen neue Abbildungen ins cda. Hier wird beschreiben, wie das Vorgehen zur Integration ist.

Die Abbildungen müssen in folgendem Verzeichnis abgelegt werden:
```
/home/mkpacc/CURRENT_IMPORT/_source
```

Hier werden dann die Abbildungen als *.tif Dateien in der korrekten Ordnerstruktur des Objekts hinterlegt, z.B.:

```
PRIVATE_NONE-P642_FR-none
  01_Overall
    PRIVATE_NONE-P642_FR-none_2024_Overall.tif
    PRIVATE_NONE-P642_FR-none_2024_Overall-001.tif
  03_IRR
    PRIVATE_NONE-P642_FR-none_2024_IRR.tif
  05_UV-light
    PRIVATE_NONE-P642_FR-none_2024_UV-fluorescence.tif
```

Es müssen nur Verzeichnisse angelegt werden, wenn auch Abbildungen enthalten sind.

## Ergänzungen zu vorhandenen
Meistens werden bestehnde Objekte um Abbildungen ergänzt. Diese liegen dann in folgendem  Unterverzeichnis:
```
/home/mkpacc/CURRENT_IMPORT/_source/01_ERGAENZEN_ZU_VORHANDENEN
```

## Dateien die ersetzen oder in andere Reihenfolge bringen
Dann gibt es den Fall, das Objekte im Abbildungen ergänzt werde, sich aber die Reihenfolge der Abbildungen ändert oder das Abbildungen ersetzt werden.

### Abbildungen ersetzen
Diese Dateien liegen in folgendem Unterverzeichnis:
```
/home/mkpacc/CURRENT_IMPORT/_source/02_ZUERST_LOESCHEN_oder_UMBENENNEN_DANN_EINFUEGEN
```
**Achtung: der Verzeichnisname muss korrekt sein. **

In diesem Verzeichnis liegen dann, neben den Abbildungen zwei CSV Dateien: `rename-items.csv` und `remove-items.csv`.

#### rename-items.csv
Enthält die Dateien, die umbenannt werden sollen. Pro Zeile jeweils der alte und dann der neue Dateiname ohne Dateisuffix. Die Werte werden mit Semikolon getrennt.
```
DE_SKMT-Lost_L-VI-1g40_FR110D_Overall;DE_SKMT-Lost_L-VI-1g40_FR110D_Overall-001
PRIVATE_NONE-P236_FR-none_2018_Overall;PRIVATE_NONE-P236_FR-none_2018_Overall-001
PRIVATE_NONE-P447_FR-none_Overall;PRIVATE_NONE-P447_FR-none_Overall-001
PRIVATE_NONE-P193_FR-none_2013_Overall;PRIVATE_NONE-P193_FR-none_2013_Overall-001
PRIVATE_NONE-P071_FR-none_2016_Overall;PRIVATE_NONE-P071_FR-none_2016_Overall-003
```

#### remove-items.csv
Enthält die Dateien, die vor dem Update gelöscht werden sollen. Pro Zeile ein Dateiname ohne Dateisuffix:

```
AR_MNdBABA_8632_FR-none_c1972_Overall
DE_AMF-MFFF_M3-M_FR156_Overall
F_MAD_PE152_FR-none_Overall
```

## Update vorbereiten
Dazu gibt es im Verzeichnis `/var/www/shared/cranach-image-tools` das Skript `prepare-image-update.php`. Das so oft angestoßen werden, bis alle Steps durchlaufen sind:
```
php prepare-image-update.php
```
**Achtung: hier scheint es beim Umbennen noch Probleme zu geben. Das beim nächsten Update unbedingt checken.**

Nach dem Durchlaufen aller Schritte liegen im Verzeichnis `/home/mkpacc/CURRENT_IMPORT/_merged-source` die vollständigen Objektverzeichnisse mit allen Bestandsbildern. Das Löschen und Umbennen hat dann bereits statt gefunden.



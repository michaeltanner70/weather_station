# Konvention für Knotenordner

Jeder Knoten hat einen eigenen Ordner unter `nodes/`. Der Ordnername ist
zugleich der Knotenname (Kleinbuchstaben, Bindestriche, z. B. `garten-regen`).
Pflichtdateien und Versionierung: siehe [projekt.md](../projekt.md).

## ESPHome-Knoten

```
nodes/<knoten>/
  README.md          Zweck, Sensoren, Verdrahtung, Version
  CHANGELOG.md
  POSTEINGANG.md     Aufträge von anderen Bereichen (entsteht mit dem ersten)
  <knoten>.yaml      ESPHome-Konfiguration
  secrets.yaml       gitignoriert
```

Gemeinsame Bausteine kommen aus `shared/esphome/` über `packages:`.

## PlatformIO-Knoten (LoRa)

```
nodes/<knoten>/
  README.md          Zweck, Sensoren, Verdrahtung, Stromversorgung, Version
  CHANGELOG.md
  POSTEINGANG.md     Aufträge von anderen Bereichen (entsteht mit dem ersten)
  platformio.ini
  src/
  include/secrets.h  gitignoriert, Vorlage als secrets.example.h
```

Das Paketformat wird aus `shared/protocol/` eingebunden.

## Zugangsdaten

Echte Werte (WLAN, API-Schlüssel, LoRa-Schlüssel) stehen nur in `secrets.yaml`
bzw. `secrets.h`. Beide Namen sind in `.gitignore` erfasst. Ins Repo gehen nur
Vorlagen mit Platzhaltern.

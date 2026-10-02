# zentrale

**Version:** 0.1.0 · Änderungen: [CHANGELOG.md](CHANGELOG.md)

ESPHome-Knoten. Empfängt die Pakete der LoRa-Knoten, liest direkt
angeschlossene Kabel-Sensoren und meldet alle Werte an Home Assistant.

## Stand

Grundgerüst ohne Sensoren und ohne LoRa. Die Konfiguration bringt den Knoten
ins WLAN und verbindet ihn mit Home Assistant.

## Hardware

Noch offen. In `zentrale.yaml` steht vorläufig ein generisches ESP32-Board
(`esp32dev`). Sobald die Hardware feststeht, werden hier Board, Funkmodul und
Verdrahtung eingetragen.

## Inbetriebnahme

1. `secrets.yaml.example` nach `secrets.yaml` kopieren und ausfüllen.
   `secrets.yaml` ist gitignoriert.
2. Konfiguration prüfen: `esphome config zentrale.yaml`
3. Flashen: `esphome run zentrale.yaml`
4. In Home Assistant das gefundene ESPHome-Gerät mit dem API-Schlüssel hinzufügen.

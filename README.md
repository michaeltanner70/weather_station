# weather_station

Wetterstation mit Zentraleinheit und abgesetzten Sensorknoten, angebunden per Kabel oder LoRa.
Die Messwerte landen in Home Assistant.

## Aufbau des Repos

```
docs/              Architektur, Konventionen, Paketformat
shared/protocol/   LoRa-Paketformat, gemeinsam für Knoten und Zentrale
shared/esphome/    Wiederverwendbare ESPHome-Pakete
nodes/<knoten>/    Ein Ordner pro Knoten, die Zentrale eingeschlossen
```

Verbindliche Abmachungen (Versionierung, Pflichtdateien): [projekt.md](projekt.md).

Jeder Knoten ist in sich abgeschlossen und hat ein eigenes README.
Wie ein Knotenordner aufgebaut ist, steht in [docs/knoten.md](docs/knoten.md).

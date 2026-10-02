# Architektur

```
Sensoren (I2C, 1-Wire, RS485 …) ──Kabel──┐
                                         ├─► Zentrale (ESPHome) ──Netz──► Home Assistant
LoRa-Knoten (PlatformIO) ────LoRa────────┘
```

## Rollen

| Rolle         | Firmware            | Anbindung                     |
|---------------|---------------------|-------------------------------|
| Zentrale      | ESPHome             | Netz zu Home Assistant        |
| Kabel-Knoten  | ESPHome             | I2C, 1-Wire, RS485 … je nach Sensor |
| LoRa-Knoten   | PlatformIO/Arduino  | LoRa zur Zentrale             |

## Datenfluss

1. Kabel-Sensoren hängen an der Zentrale oder an einem eigenen ESPHome-Knoten
   und erscheinen direkt als Entitäten in Home Assistant.
2. LoRa-Knoten wachen auf, messen, senden ein Paket und schlafen wieder.
3. Die Zentrale empfängt das Paket, prüft es und gibt die Werte als Entitäten
   an Home Assistant weiter.

## LoRa-Paketformat

Wird in `shared/protocol/` festgelegt und gilt für alle Knoten und die Zentrale.
Geplant sind:

- Knoten-ID, Paketzähler und Batteriespannung
- Messwerte in kompakter Binärform, damit die Sendezeit kurz bleibt
- eine Prüfsumme und ein gemeinsamer Schlüssel, damit fremde Pakete verworfen werden

## Ausweichweg

Reicht der LoRa-Empfang in ESPHome nicht aus, übernimmt ein eigener Gateway mit
PlatformIO den Empfang und meldet per MQTT an Home Assistant. Das Paketformat
bleibt dabei gleich.

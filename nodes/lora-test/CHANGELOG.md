# Changelog

Alle Änderungen an diesem Knoten. Aufbau nach
[Keep a Changelog](https://keepachangelog.com/de/1.1.0/), Versionierung nach
[projekt.md](../../projekt.md).

## [Unveröffentlicht]

## [0.1.0] – 2026-10-02

Erster Stand des Prototyps. Noch nicht auf der Hardware getestet.

### Hinzugefügt

- Sender `lora-sender.yaml`: ESP32 DevKitC + RF96 (SX1276), Dummy-Werte für
  Temperatur, Feuchte, Luftdruck, Wind, Windrichtung, Regen und einen
  Paketzähler, gesendet per ESPHome `packet_transport`
- Empfänger `lora-receiver.yaml`: TTGO LoRa32 V1.0, zeigt Messwerte und
  Funkstatus (RSSI, SNR, Paketalter, empfangene und verlorene Pakete) auf dem
  OLED, LED blinkt bei jedem Paket
- Funkparameter 868,1 MHz, SF9, BW 125 kHz, CR 4/5, 14 dBm, verschlüsselt,
  Sendeintervall 60 s
- Vorlage `secrets.yaml.example`

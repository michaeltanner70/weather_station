# LoRa-Prototyp Wetterstation

Prototyp für die Übertragung von Sensordaten per LoRa P2P mit ESPHome (`sx127x` + `packet_transport`, ab ESPHome 2025.7).

| Rolle | Hardware | Config |
|---|---|---|
| Sender | ESP32 DevKitC + RF96 (SX1276, 868 MHz) | `lora-sender.yaml` |
| Empfänger | TTGO LoRa32 V1.0 (SX1276, OLED) | `lora-receiver.yaml` |

## Funkparameter

868,1 MHz · SF9 · BW 125 kHz · CR 4/5 · 14 dBm (25 mW) · verschlüsselt

## Verdrahtung Sender

| RF96 | DevKitC |
|---|---|
| SCK | GPIO18 |
| MISO | GPIO19 |
| MOSI | GPIO23 |
| NSS | GPIO5 |
| RST | GPIO14 |
| DIO0 | GPIO26 |
| VCC / GND | 3V3 / GND |

Antenne immer vor dem Einschalten anschliessen (λ/4-Draht ≈ 8,2 cm).

## Inbetriebnahme

1. `secrets.yaml.example` nach `secrets.yaml` kopieren und ausfüllen.
2. Beide Configs flashen.
3. Empfänger-Log und OLED prüfen: Seite «Wetter» zeigt Werte, Seite «Funk» zeigt RSSI, SNR, Paketalter, Empfangs- und Verlustzähler. GPIO0 (Taster) schaltet die Seite weiter, die LED blinkt bei jedem Paket.

## Duty Cycle

Im Band 868,0–868,6 MHz gilt 1 % Duty Cycle (36 s Sendezeit pro Stunde). Ein Paket mit rund 60 Bytes braucht bei SF9 etwa 370 ms. Bei 30 s Intervall wären das gut 1,2 %, deshalb sendet der Prototyp alle 60 s (≈ 0,6 %). Die tatsächliche Paketgrösse steht im Empfänger-Log.

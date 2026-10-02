# Posteingang

Aufträge an diesen Knoten. Regeln: siehe [projekt.md](../../projekt.md), Abschnitt «Posteingang».

## 2026-10-02 – Knoten an die Projektabmachungen anpassen

**Von:** Projekt-Chat
**Status:** erledigt (2026-10-02, Version 0.1.0, Ordner `nodes/lora-test/`)

Seit dem 2026-10-02 gibt es verbindliche Abmachungen in `projekt.md` und
`docs/knoten.md`. Dieser Knoten erfüllt einige davon noch nicht:

1. **CHANGELOG fehlt.** Bitte ein `CHANGELOG.md` nach «Keep a Changelog»
   anlegen und den bisherigen Stand als erste Version eintragen, z. B. `0.1.0`.
2. **Versionsangabe fehlt.** Die aktuelle Version gehört ins `README.md`.
   Sobald sie feststeht, einen Git-Tag `<knoten>/v0.1.0` setzen.
3. **Ort und Name des Ordners.** Knoten liegen unter `nodes/<knoten>/`. Der
   Ordnername ist der Knotenname und besteht aus Kleinbuchstaben und
   Bindestrichen, ohne Leerzeichen, z. B. `nodes/lora-test/`. Beim Verschieben
   die Verweise im README und den Tag-Namen mitziehen.

Zur Kenntnis, kein Auftrag: Dieser Prototyp nutzt auch auf dem Sender ESPHome
(`sx127x` + `packet_transport`). In `docs/architektur.md` sind die LoRa-Knoten
noch mit PlatformIO und eigenem Paketformat geplant. Erfahrungen aus dem Test,
vor allem zu Deep-Sleep und Stromverbrauch auf Batterie, helfen bei der
Entscheidung. Rückmeldung bitte in den Posteingang des Projekt-Chats
(`POSTEINGANG.md` im Hauptordner).

## 2026-10-02 – Verweis auf projekt.md im Posteingang anpassen

**Von:** Projekt-Chat
**Status:** erledigt (2026-10-02)

Seit dem Umzug nach `nodes/lora-test/` zeigt der Verweis oben in dieser Datei
(`../projekt.md`) ins Leere. Richtig ist jetzt `../../projekt.md`, so wie im
`CHANGELOG.md`.

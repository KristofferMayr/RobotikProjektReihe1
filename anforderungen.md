# 2. Systemanforderungen

## Funktionale Anforderungen
- **Sensorik:** Kontinuierliche Messung der Bodenfeuchtigkeit und der Lufttemperatur/Luftfeuchtigkeit.
- **Aktorik:** Automatisches Einschalten einer Wasserpumpe bei Unterschreitung der Bodenfeuchte.
- **Lüftung:** Aktivierung eines Lüfters bei Überschreitung einer Temperaturschwelle.
- **Monitoring:** Ausgabe der aktuellen Werte über ein I2C-Display.

## Nicht-funktionale Anforderungen
- **Zuverlässigkeit:** Das System muss 24/7 stabil laufen.
- **Einfache Wartung:** Komponenten müssen leicht austauschbar sein.
- **Energieeffizienz:** Geringer Stromverbrauch im Standby-Modus.

## Echtzeit-Einordnung
**Weiches Echtzeitsystem.** 
- *Begründung:* Die biologischen Prozesse der Pflanzen reagieren langsam. Eine Reaktionszeit von 500ms bis 2s für die Aktivierung der Pumpe ist völlig ausreichend. Ein Überschreiten dieser Zeitschranke führt nicht zum Absterben der Pflanze oder zur Zerstörung der Hardware.

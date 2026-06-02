# 5. Regelkreis-Beschreibung

## Bewässerungs-Regelkreis (Zweistandregler)

- **Regelgröße:** Bodenfeuchtigkeit (in %).
- **Sollgröße:** Definiertes Feuchtigkeitslevel (z.B. > 40%).
- **Sensor / Istwerterfassung:** Kapazitiver Bodenfeuchtesensor.
- **Regler:** Softwareseitiger Hystereseregler (Zweistandregler) auf dem ESP32.
- **Aktor / Stellglied:** 5V Wasserpumpe (über Relais geschaltet).

### Funktionsweise
Wenn der gemessene Analogwert eine untere Schwelle unterschreitet (Boden zu trocken), schaltet der ESP32 das Relais ein. Sobald die Feuchtigkeit einen oberen Schwellenwert erreicht, wird die Pumpe wieder abgeschaltet.

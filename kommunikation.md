# 6. Kommunikationskonzept

## Verwendete Protokolle
- **I2C (Inter-Integrated Circuit):** Wird für die Anbindung des LCD-Displays verwendet. 
  - *Warum?* Spart Pins am ESP32 und ist standardisiert für Display-Controller.
- **Analoge Signale:** Der Bodenfeuchtesensor liefert eine Spannung zwischen 0-3.3V an den ADC des ESP32.
  - *Warum?* Kostengünstig und präzise genug für Feuchtigkeitsmessungen.
- **Digital (OneWire-ähnlich):** Der DHT22 nutzt ein spezifisches digitales Protokoll.
- **PWM / Digital Out:** Zur Ansteuerung des Relais (Pumpe) und des Transistors (Lüfter).

## Eignung
Diese Protokolle sind für ein eingebettetes System dieser Größe ideal, da sie vom ESP32 nativ unterstützt werden und die Verkabelung minimal halten.

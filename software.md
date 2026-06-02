# 7. Softwarekonzept

## Entwicklungswerkzeuge
- **IDE:** Visual Studio Code mit **PlatformIO**. Grund ist die bessere Verwaltung von Bibliotheken und die Unterstützung professioneller Workflows im Vergleich zur Standard-Arduino-IDE.
- **Programmiersprache:** C++ (Arduino Framework).

## Bibliotheken
- `DHT sensor library` (Adafruit): Zur einfachen Auslesung des DHT22 Sensors.
- `LiquidCrystal_I2C`: Zur Steuerung des Displays über den I2C-Bus.
- `WiFi.h`: Falls zukünftig eine Cloud-Anbindung (z.B. MQTT) für das Monitoring implementiert wird.

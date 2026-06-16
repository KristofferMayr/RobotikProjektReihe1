# 7. Softwarekonzept

## 7.1 Entwicklungsumgebung

Für die Umsetzung des Tischtennisroboters wird eine Kombination aus Echtzeitsteuerung und leistungsfähiger Bildverarbeitung benötigt. Daher wird die Software auf zwei Ebenen aufgeteilt:

### Mikrocontroller-Ebene (Echtzeitsteuerung)

**IDE:** Arduino IDE oder PlatformIO (Visual Studio Code)

**Programmiersprache:** C++

**Aufgaben:**

* Ansteuerung der Servomotoren
* Echtzeit-Regelung der Gelenkpositionen
* Überwachung der Sicherheitssysteme
* Kommunikation mit dem Bildverarbeitungsrechner

**Vorteile:**

* Direkter Hardwarezugriff
* Hohe Ausführungsgeschwindigkeit
* Große Auswahl an Bibliotheken
* Gute Unterstützung für Echtzeitanwendungen

### Bildverarbeitungs-Ebene

**IDE:** Visual Studio Code

**Programmiersprache:** Python

**Aufgaben:**

* Verarbeitung der Kamerabilder
* Erkennung und Tracking des Tischtennisballs
* Berechnung der Flugbahn
* Schnitterkennung
* Übergabe der Zielkoordinaten an die Robotersteuerung

**Vorteile:**

* Schnelle Entwicklung
* Große Auswahl an KI- und Computer-Vision-Bibliotheken
* Gute Unterstützung für wissenschaftliche Berechnungen

---

## 7.2 Softwarearchitektur

Die Software wird in mehrere Module unterteilt:

### Modul 1: Bildaufnahme

**Aufgabe:**

* Empfang der Kamerabilder
* Vorverarbeitung der Bilddaten
* Synchronisation mehrerer Kameras

**Eingaben:**

* Videostream der High-Speed-Kameras

**Ausgaben:**

* Vorverarbeitete Bilddaten

---

### Modul 2: Ballerkennung und Tracking

**Aufgabe:**

* Erkennung des Tischtennisballs
* Bestimmung der Position im Raum
* Verfolgung der Bewegung über mehrere Bilder

**Eingaben:**

* Bilddaten der Kameras

**Ausgaben:**

* Aktuelle X-, Y- und Z-Koordinaten

---

### Modul 3: Flugbahn- und Schnittberechnung

**Aufgabe:**

* Berechnung der zukünftigen Flugbahn
* Ermittlung des Treffpunkts
* Schätzung des Ballschnitts (Topspin, Backspin, Sidespin)

**Eingaben:**

* Ballpositionen
* Geschwindigkeitsvektoren

**Ausgaben:**

* Vorhergesagter Treffpunkt
* Geschätzter Ballspin

---

### Modul 4: Bewegungsplanung

**Aufgabe:**

* Berechnung der optimalen Roboterbewegung
* Planung des Schlages
* Erzeugung der Gelenksollwerte

**Eingaben:**

* Treffpunkt
* Gewünschte Schlagart

**Ausgaben:**

* Gelenkwinkel
* Geschwindigkeitsprofile

---

### Modul 5: Motorsteuerung

**Aufgabe:**

* Umsetzung der Sollwerte in Motorbewegungen
* Regelung der Gelenkpositionen
* Überwachung der Motoren

**Eingaben:**

* Sollpositionen

**Ausgaben:**

* PWM-Signale bzw. Servo-Kommandos

---

### Modul 6: Sicherheitsmodul

**Aufgabe:**

* Überwachung des Not-Aus-Systems
* Kollisionsvermeidung
* Sofortige Abschaltung bei Gefahr

**Eingaben:**

* Sicherheits- und Näherungssensoren

**Ausgaben:**

* Abschaltsignal

---

## 7.3 Verwendbare Bibliotheken

### Für die Bildverarbeitung (Python)

| Bibliothek | Zweck                                 |
| ---------- | ------------------------------------- |
| OpenCV     | Bildverarbeitung und Objekterkennung  |
| NumPy      | Mathematische Berechnungen            |
| SciPy      | Flugbahn- und Bewegungsberechnungen   |
| PyTorch    | KI-gestützte Ballerkennung (optional) |

### Für die Mikrocontroller-Software (C++)

| Bibliothek   | Zweck                           |
| ------------ | ------------------------------- |
| Servo.h      | Servomotorsteuerung             |
| AccelStepper | Präzise Bewegungssteuerung      |
| PID Library  | Implementierung der Regelkreise |
| CAN Library  | Kommunikation über CAN-Bus      |

---

## 7.4 Kommunikationsschnittstellen

### UART

Verbindung zwischen Bildverarbeitungsrechner und Mikrocontroller.

**Übertragene Daten:**

* Ballposition
* Treffpunkt
* Schlagparameter

### CAN-Bus

Kommunikation zwischen Steuerung und Motorcontrollern.

**Vorteile:**

* Hohe Zuverlässigkeit
* Echtzeitfähig
* Störsicher

---

## 7.5 Echtzeitanforderungen

Da es sich um ein hartes Echtzeitsystem handelt, müssen bestimmte Zeitgrenzen eingehalten werden:

| Aufgabe                | Maximale Zeit |
| ---------------------- | ------------- |
| Ballerkennung          | ≤ 5 ms        |
| Flugbahnberechnung     | ≤ 5 ms        |
| Bewegungsplanung       | ≤ 5 ms        |
| Motorregelung          | ≤ 1 ms        |
| Sicherheitsabschaltung | ≤ 2 ms        |

Werden diese Zeitvorgaben überschritten, kann der Ball nicht mehr korrekt getroffen werden oder es entstehen Sicherheitsrisiken.

---

## 7.6 Test- und Simulationswerkzeuge

Vor dem Aufbau eines Prototyps kann die Software mit folgenden Werkzeugen getestet werden:

* Gazebo (Robotersimulation)
* ROS 2 (Robot Operating System)
* OpenCV-Testumgebung mit aufgezeichneten Kamerabildern
* PlatformIO Debugger für die Mikrocontroller-Software

Dadurch können Bewegungsabläufe, Flugbahnberechnungen und Sicherheitsfunktionen bereits vor der realen Inbetriebnahme überprüft werden.

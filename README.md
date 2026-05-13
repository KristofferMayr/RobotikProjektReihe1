# Projektaufgabe: Planung eines eingebetteten Robotersystems

Im Unterricht haben wir die theoretischen Grundlagen zu folgenden Themen erarbeitet:

- Embedded Systems
- Robotik
- Kommunikations-Schnittstellen

Eure Aufgabe ist es, als Team einen kleinen, funktionalen Roboter zu planen. Es wird kein physischer Aufbau erwartet. Stattdessen erstellt ihr eine vollständige, realistische Planungsmappe auf Basis echter, verfügbarer Bauteile.

> Wichtig: Der geplante Roboter muss realistisch umsetzbar sein. Alle gewählten Komponenten müssen real existieren und miteinander kompatibel sein. Verwendete Datenblätter und Preisquellen sind anzugeben.

## Ziele der Aufgabe

- Theoretisches Wissen aus allen drei Themenbereichen anwenden und verknüpfen
- Eigenverantwortlich Komponenten recherchieren und auf Kompatibilität prüfen
- Ein technisches System ganzheitlich denken, von der Sensorik bis zur Kommunikation
- Technische Entscheidungen begründen und dokumentieren

## Anforderungen an den geplanten Roboter

Der geplante Roboter muss folgende Mindestanforderungen erfüllen:

| Anforderung | Details |
| --- | --- |
| Freiheitsgrade | Mindestens 2, maximal 6 Freiheitsgrade |
| Regelkreis | Mindestens 1 geschlossener Regelkreis, z. B. Positionsregelung |
| Sensorik | Mindestens 2 verschiedene Sensortypen |
| Kommunikation | Mindestens 1 Kommunikationsprotokoll zwischen Komponenten, z. B. CAN, I²C |
| Steuerung | Microcontroller als zentrale Steuereinheit |
| Echtzeit | Einordnung und Begründung als hartes oder weiches Echtzeitsystem |

## Inhalt der Planungsmappe

Die Planungsmappe ist als GitHub Repository abzugeben und muss folgende Abschnitte enthalten:

### 1. Projektbeschreibung

- Was soll der Roboter tun?
- Welches Problem löst er?
- In welchem Umfeld wird er eingesetzt? Industrie, Haushalt, Labor, ...
- Warum habt ihr diesen Anwendungsfall gewählt?
- Einordnung: stationärer oder mobiler Roboter? Warum?

### 2. Systemanforderungen

Definiert die Anforderungen an euer System strukturiert:

- Funktionale Anforderungen: Was muss der Roboter können?
- Nicht-funktionale Anforderungen: Geschwindigkeit, Genauigkeit, Zuverlässigkeit, Umgebungsbedingungen
- Echtzeit-Einordnung: Hartes oder weiches Echtzeitsystem? Begründung mit konkreten Zeitschranken, z. B. „Die Kollisionserkennung muss innerhalb von X ms reagieren, weil...“

### 3. Komponentenliste

Erstellt eine vollständige Stückliste aller benötigten Bauteile. Hier ein Vorschlag für den Aufbau:

| Bauteil | Bezeichnung / Modell | Funktion im System | Spannung | Schnittstelle | Preis (€) | Quelle / Datenblatt |
| --- | --- | --- | --- | --- | --- | --- |
| Microcontroller | z. B. Arduino MEGA 2560 | Zentrale Steuereinheit | 5V | SPI, I²C, UART | 12,90 | [Link] |
| Motor 1 | ... | ... | ... | ... | ... | ... |
| Sensor 1 | ... | ... | ... | ... | ... | ... |

Gesamt: XX,XX €

Empfohlene Quellen: Reichelt, Mouser, DigiKey, Conrad, Roboter-Bausatz.de, RS Components.

### 4. Systemarchitektur – Breadboard-Layout

Erstellt ein oder mehrere Breadboard-Layouts des Gesamtsystems. Das Layout kann mit einem beliebigen Tool erstellt werden, z. B. Cirkit Designer.

### 5. Regelkreis-Beschreibung

Beschreibt mindestens einen Regelkreis eures Systems detailliert:

- Regelgröße: Was wird geregelt? z. B. Position, Geschwindigkeit
- Sollgröße: Wie wird der Sollwert vorgegeben?
- Sensor / Istwerterfassung: Welches Bauteil liefert den Messwert?
- Regler: Welcher Reglertyp wird eingesetzt?
- Aktor / Stellglied: Was bewirkt die Regelung physisch?
- Skizze des Regelkreises

### 6. Kommunikationskonzept

Beschreibt, wie die Komponenten eures Systems miteinander kommunizieren:

- Welche Protokolle werden verwendet und warum? CAN, I²C, UART, PWM, GPIO, ...
- Warum ist das gewählte Protokoll für euren Anwendungsfall geeignet?

### 7. Softwarekonzept

Beschreibe, welche Entwicklungswerkzeuge zum Einsatz kommen:

- Welche IDEs bzw. Programmiersprachen bieten sich für eure Umsetzung an?
- Welche Bibliotheken gibt es und können eingesetzt werden, um die Umsetzung eines Prototypen möglichst einfach zu gestalten?

## Struktur des GitHub Repositories

```text
...-[gruppenname]/
├── README.md                  ← Projektbeschreibung (Abschnitt 1)
├── anforderungen.md           ← Systemanforderungen (Abschnitt 2)
├── komponenten.md             ← Komponentenliste (Abschnitt 3)
├── kommunikation.md           ← Kommunikationskonzept (Abschnitt 6)
├── regelkreis.md              ← Regelkreis-Beschreibung (Abschnitt 5)
├── software.md                ← Softwarekonzept (Abschnitt 7)
│
├── diagramme/
│   ├── layout.png             ← Systemarchitektur (Abschnitt 4)
│   └── regelkreis.png         ← Regelkreisskizze
│
└── quellen/
    └── quellen.md             ← Alle verwendeten Quellen und Datenblätter
```

## Bewertungskriterien

| Kriterium | Gewichtung | Beschreibung |
| --- | --- | --- |
| Fachliche Korrektheit | 35 % | Stimmen Spannungen, Schnittstellen und Spezifikationen? Sind die Komponenten wirklich kompatibel? Ist die Echtzeit-Einordnung korrekt begründet? |
| Systemdenken | 30 % | Wird das System als Ganzes gedacht? Ist das Blockschaltbild vollständig und konsistent? Ist der Regelkreis korrekt beschrieben? |
| Kreativität & Originalität | 20 % | Wie interessant und eigenständig ist der gewählte Anwendungsfall? Gibt es besondere Lösungsansätze? |
| Dokumentation & Struktur | 15 % | Ist das Repository sauber strukturiert? Sind alle Pflichtabschnitte vollständig? Sind Quellen korrekt angegeben? |

## Wichtige Hinweise

- Keine Fantasiebauteile. Alle Komponenten müssen real existieren und kaufbar sein. Gebt immer eine Quelle an.
- Kompatibilität prüfen. Achtet auf Betriebsspannungen, Stromaufnahme, Kommunikationsschnittstellen und mechanische Kompatibilität.
- Scope beachten. Ein zu einfaches System, z. B. 1 Servo und 1 Button, wird genauso niedrig bewertet wie ein unrealistisch komplexes System, z. B. ein humanoider Roboter mit KI.
- Eigenständige Arbeit. Gruppenarbeit bedeutet gemeinsames Denken, nicht Aufteilen und Zusammenkopieren. Im Abgabegespräch muss jedes Gruppenmitglied alle Entscheidungen erklären können.
- Abgabegespräch: Nach der Abgabe findet ein kurzes Abgabegespräch, ca. 10 Minuten pro Gruppe, statt, in dem Fragen zu den getroffenen Entscheidungen gestellt werden.
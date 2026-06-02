## 2. Systemanforderungen


### 2.1 Funktionale Anforderungen (Was muss der Roboter können?)
Die funktionalen Anforderungen beschreiben die konkreten Aufgaben und Fähigkeiten, die das System implementieren muss:

* **FA01: Ballerkennung und -tracking:** Das System muss den Tischtennisball mittels Computer Vision in Echtzeit im dreidimensionalen Raum erfassen (X-, Y-, Z-Koordinaten).
* **FA02: Flugbahnberechnung:** Das System muss aus den getrackten Punkten die zukünftige Flugbahn des Balls im Voraus berechnen (Prädiktion), inklusive der Berechnung des voraussichtlichen Aufprallpunkts auf der Platte und des Treffpunkts im Raum.
* **FA03: Schnitterkennung:** Der Roboter muss den Drall des ankommenden Balls (Topspin, Backspin, Sidespin) anhand der Flugbahnveränderung (Magnus-Effekt) oder der Ballrotation erkennen.
* **FA04: Dynamische Schlaggenerierung:** Der Roboterarm muss den Schläger rechtzeitig zum berechneten Treffpunkt bewegen und eine koordinierte Schlagbewegung (Ausholen, Treffen, Durchziehen) ausführen.
* **FA05: Schnittgenerierung (Effet):** Der Roboter muss in der Lage sein, durch eine gezielte Handgelenks- oder Rotationsbewegung im Moment des Ballkontakts eigenen Schnitt (z. B. Topspin für einen Angriffsschlag) zu erzeugen.
* **FA06: Sicherheitsabschaltung:** Das System muss über eine Not-Aus-Funktion (software- und hardwareseitig) verfügen, die die Motoren sofort stromlos schaltet, wenn eine Person den Sicherheitsbereich betritt.

### 2.2 Nicht-funktionale Anforderungen
Die nicht-funktionalen Anforderungen definieren die Qualitätsattribute und Rahmenbedingungen des Systems:

* **NFA01: Geschwindigkeit (Dynamik):** Die Antriebe des Roboterarms müssen extrem hohe Beschleunigungen (z. B. $> 10 \text{ m/s}^2$) und Endgeschwindigkeiten erreichen, um den Schläger innerhalb von Bruchteilen einer Sekunde zu positionieren.
* **NFA02: Genauigkeit (Präzision):** Die Positionierungsgenauigkeit des Schlägers am Treffpunkt muss innerhalb einer Toleranz von maximal $\pm 5 \text{ mm}$ liegen, da minimale Abweichungen im Schlägerwinkel zu Fehlflügen des Balls führen.
* **NFA03: Zuverlässigkeit (Trefferquote):** Das System muss bei Standardbällen (ohne extremen, unberechenbaren Schnitt) eine Trefferquote von mindestens 90 % im kontinuierlichen Spielbetrieb erreichen.
* **NFA04: Umgebungsbedingungen:** * Das System ist für den Betrieb in Innenräumen (Vermeidung von Windströmen, die die Ballbahn verfälschen) bei normaler Raumtemperatur ($15^\circ\text{C}$ bis $30^\circ\text{C}$) ausgelegt.
    * Die Bildverarbeitung erfordert konstante, flackerfreie Lichtverhältnisse (z. B. LED-Beleuchtung mit hoher Frequenz), um Frame-Verluste der High-Speed-Kameras zu verhindern.

### 2.3 Echtzeit-Einordnung
Es handelt sich bei diesem Projekt um ein **hartes Echtzeitsystem** (*Hard Real-Time System*).

**Begründung:**
Ein Verpassen einer vorgegebenen Zeitschranke (Deadline) führt bei diesem System nicht nur zu einer verminderten Qualität, sondern zum **totalen Systemversagen** (der Ball wird komplett verfehlt, der Punkt geht verloren).

**Konkrete Zeitschranken:**
1.  **Flugbahnberechnung und Trajektorienplanung ($\le 5 \text{ ms}$):** Nach dem Ballaufsprung auf der gegnerischen Seite verbleiben dem Ball bis zum Erreichen des Roboters nur ca. 200 bis 400 Millisekunden. Die Bildverarbeitung und die Berechnung der Roboterbewegung müssen innerhalb von maximal 5 ms nach dem Erkennen des Balles abgeschlossen sein, damit dem Arm genügend mechanische Zeit für die Anfahrt bleibt.
2.  **Zykluszeit der Motorregelung ($\le 1 \text{ ms}$):** Die Servocontroller müssen im Millisekundentakt mit neuen Sollwerten gefüttert werden. Eine Verzögerung führt zu unkontrolliertem Ruckeln oder Schwingungen des Arms, was bei den hohen Geschwindigkeiten die Mechanik zerstören würde.
3.  **Kollisionserkennung und Sicherheitsstopp ($\le 2 \text{ ms}$):** Tritt ein unerwartetes Hindernis auf (z. B. der Spieler greift über das Netz), muss die Kollisionserkennung innerhalb von 2 ms reagieren und den Bremsvorgang einleiten, da bei den auftretenden Kräften akute Verletzungsgefahr für den Menschen und Zerstörungsgefahr für den Roboter besteht.
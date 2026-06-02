# 1. Projektbeschreibung

## 1.1 Was soll der Roboter tun?
Der Roboter ist ein hochdynamischer, automatisierter Roboterarm, der eigenständig Tischtennis gegen einen menschlichen Partner oder einen anderen Roboter spielen kann. Mithilfe eines integrierten Kamerasystems (*Computer Vision*) erfasst der Roboter die Flugbahn des Balls in Echtzeit, berechnet den optimalen Treffpunkt und führt eine präzise Schlagbewegung aus. 

Eine technologische Besonderheit des Systems ist die Fähigkeit, dem Ball durch eine gezielte Bewegung des Schlägers beim Treffpunkt eigenen Drall (*Schnitt wie Topspin, Backspin oder Sidespin*) zu verleihen sowie auf den ankommenden Schnitt des Gegners adäquat zu reagieren.

## 1.2 Welches Problem löst er?
Im Tischtennis-Training ist es oft schwierig, konstante und gleichzeitig unvorhersehbare Spielbedingungen zu simulieren:
* **Einschränkung herkömmlicher Maschinen:** Klassische Tischtennis-Ballmaschinen (die Bälle lediglich mechanisch auswerfen) erlauben kein realistisches Match-Szenario, da sie starr sind und nicht auf den tatsächlichen Rückschlag des Spielers reagieren.
* **Die Lösung:** Unser Roboter schließt die Lücke zwischen monotonem Ballauswurf und einem menschlichen Spielpartner. Er stellt einen intelligenten, adaptiven Trainingspartner dar, der komplexe Schnittvariationen und Flugbahnen fehlerfrei, unermüdlich und reproduzierbar beherrscht.

## 1.3 In welchem Umfeld wird er eingesetzt?
* **Sport- und Freizeitbereich:** Einsatz in Vereinen und Trainingszentren zur Nachwuchs- und Profiförderung 

## 1.4 Warum habt ihr diesen Anwendungsfall gewählt?
Die Motivation hinter diesem Anwendungsfall liegt in der enormen technischen und interdisziplinären Herausforderung. Inspiriert von modernen Technologiedemonstratoren (wie den Systemen von Sony) verbindet dieses Projekt mehrere Disziplinen der Spitzentechnologie:


## 1.5 Einordnung: Stationärer oder mobiler Roboter?
Es handelt sich um einen **stationären Roboter**.

**Begründung:**
Der Roboterarm wird fest am Ende oder leicht hinter der Tischtennistischplatte montiert. Da der Aktionsradius des Arms vollständig ausreicht, um die gesamte Breite und Höhe der eigenen Tischhälfte abzudecken, ist eine mobile Basis (wie Räder oder Schienen) nicht erforderlich. Eine feste mechanische Verankerung garantiert zudem die maximale Stabilität und Wiederholgenauigkeit bei den extrem schnellen und beschleunigungsintensiven Schlagbewegungen. Ein mobiles System würde hierbei zu stark schwingen und massiv an Präzision verlieren.
# 3. Komponentenliste

| Bauteil | Bezeichnung / Modell | Funktion im System | Spannung | Schnittstelle | Preis (€) | Quelle / Datenblatt |
|---|---|---|---|---|---|---|
| Industrie-PC | Beckhoff C6030 | Zentrale Steuereinheit, Trajektorienberechnung & EtherCAT Master (RT-Linux) | 24V DC | EtherCAT, 4x GigE | 1.450,00 | [Beckhoff C6030] |
| Co-Prozessor (KI) | NVIDIA RTX 4060 | CUDA-beschleunigte 3D-Ballerkennung und Vorhersage in Echtzeit | 12V DC (PCIe) | PCIe x16 | 329,00 | [NVIDIA Spec] |
| Kamera 1 & 2 | 2x Basler ace2 a2A1920-160uc | Hochgeschwindigkeits-Stereo-Bilderfassung (160 fps) zur Ballortung | 12-24V DC | GigE Vision | 898,00 | [Basler ace2] |
| Kameraobjektive | 2x Kowa LM12HC F1.4 | Fixbrennweiten-Objektive (12mm) mit minimaler optischer Verzeichnung | — | C-Mount | 280,00 | [Kowa Lenses] |
| Blitz-Controller | Gardasoft PP610 | Präzise Stroboskop-Synchronisation der LEDs mit Kamera-Shutter | 24V DC | Ethernet / RS232 | 580,00 | [Gardasoft PP610] |
| LED-Beleuchtung | 2x High-Power LED-Panels | Kontrastreiche, flackerfreie Ausleuchtung der Ballflugbahn | 24V DC | Trigger-Eingang | 240,00 | [Industrie-LED] |
| Buskoppler | Beckhoff EK1100 | Kopplung der modularen EtherCAT-E/A-Klemmen mit dem IPC | 24V DC | EtherCAT (RJ45) | 175,00 | [Beckhoff EK1100] |
| Motortreiber (1-6) | 6x Beckhoff EL7211-0010 | Kompakte Servomotor-EtherCAT-Klemmen mit FOC-Regelung und STO | 48V DC | EtherCAT / CoE | 2.160,00 | [Beckhoff EL7211] |
| Hauptmotoren (M1-M3) | 3x Maxon EC-i 52 (180W) | Bürstenloser High-Torque-Antrieb für die trägen Basisachsen | 48V DC | PWM / Hall-Geber | 1.260,00 | [Maxon EC-i 52] |
| Handgelenkmotoren | 3x Maxon EC-flat 45 (70W) | Kompakte, flache BLDC-Motoren für minimales Gewicht an Handachsen | 48V DC | PWM / Hall-Geber | 780,00 | [Maxon EC-flat] |
| Hauptgetriebe (G1-G3) | 3x Harmonic Drive HFUC-20-100 | Spielfreie Wellgetriebe (100:1) für extreme Positioniergenauigkeit | — | Mechanisch | 2.850,00 | [Harmonic Drive] |
| Handgelenkgetriebe | 3x Harmonic Drive HFUC-14-50 | Leichtbau-Wellgetriebe (50:1) zur Schlägerorientierung / Drall | — | Mechanisch | 2.190,00 | [Harmonic Drive] |
| Absolut-Encoder | 6x RLS Orbis Absolute | Magnetische Absolutwertgeber direkt an den Gelenk-Abtriebswellen | 5V DC | BiSS-C / SSI | 1.320,00 | [RLS Orbis Spec] |
| Safety-SPS | Pilz PNOZmulti 2 (B0) | Hardwareseitige Überwachung der Not-Aus-Kette und STO-Kreise | 24V DC | Digitale E/A, Modbus | 540,00 | [Pilz PNOZmulti] |
| Lichtvorhang | Sick C4000 Advanced | Optoelektronische Absicherung des Gefahrenbereichs (Arbeitsraum) | 24V DC | OSSD-Kontakte | 950,00 | [Sick C4000] |
| Not-Aus-Taster | Siemens SIRIUS ACT | Pilzdrucktaster zur physischen Unterbrechung der Sicherheitskette | — | 2x Öffner (NC) | 42,00 | [Siemens SIRIUS] |
| Hauptnetzteil Motoren | Mean Well RSP-1500-48 | Schaltnetzteil zur Leistungsversorgung der Servomotoren (32A) | 230V → 48V DC | Schraubklemmen | 345,00 | [MW RSP-1500] |
| Logiknetzteil | Mean Well NDR-240-24 | Hutschienen-Netzteil für Steuerung, IPC, Safety und Sensorik | 230V → 24V DC | Schraubklemmen | 68,00 | [MW NDR-240] |
| Mechanische Struktur | Custom CFK & Aluminium | Arm-Glieder aus Carbon-Rohren und CNC-Alu-Gelenkstücken | — | Mechanisch | 1.150,00 | [Eigenkonstruktion] |
| **GESAMTSUMME** | | | | | **17.207,00 €** | |

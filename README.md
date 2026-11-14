# Draw & Flow – Physik-Demo

Browser-Demo: Striche zeichnen, Wasser/Sand regnen oder schütten lassen, Bälle setzen, Wind mit Böen. Das Verhalten ergibt sich aus einer positionsbasierten Partikelsimulation (keine Formerkennung). Maßstab: 1 m = 250 px.

Starten: `index.html` im Browser öffnen. Keine Abhängigkeiten.

## Bedienung

Schlanke Icon-Leiste oben: Zeichnen, Radieren, Ball, Schütten · Material (Wasser/Sand) · Regen · Aufgaben · Ansicht · Rückgängig · nächste Demo (1/5 … 5/5) · Pause · Zahnrad.

- **Stift und Radierer** in drei Größen: lange drücken (Maus: Rechtsklick oder erneut klicken). Der Radierer schneidet Striche nur dort auf, wo gewischt wird. Rückgängig stellt sie wieder her.
- **Zoom und Verschieben:** zwei Finger (Pinch). Am PC: Mausrad zoomt am Zeiger, rechte/mittlere Maustaste oder Leertaste + Ziehen verschiebt, Tasten `+` `−` `0`. Die Welt ist doppelt so breit und hoch wie der Bildschirm; das Rahmen-Symbol wechselt zwischen Startansicht und ganzer Welt.

Zahnrad-Menü (Einstellungen werden im Browser gespeichert):

- **Max. Wassertropfen** 500 – 10 000 (Standard 5 000); *Auto-Leistung* senkt das Budget, wenn das Gerät nicht hinterherkommt
- **Dämpfung** (Viskosität), **Präzision** (Teilschritte pro Bild), **Regenstärke**
- **Wind** und Böen, **Ball** (leicht/schwer, S/M/L), Statistik/Debug, Partikel leeren, Alles löschen

## Aufgaben (Fahnen-Symbol)

Bernsteinfarbene Striche gehören zur Aufgabe und lassen sich nicht radieren. Unten zeigt eine Leiste Fortschritt, Zeit und verbrauchte Tinte; gelöste Aufgaben werden abgehakt.

1. **Becher füllen** – eine Rinne leitet den Strahl in den Becher
2. **Ball ins Ziel** – Bahn über die Mauer in den Korb (liegt der Ball still, kommt ein neuer)
3. **Boot heben** – Wasser in den Schacht leiten, bis der Ball über die Linie schwimmt (Auftrieb)
4. **Sandburg im Wind** – in 6 s kommt Sturm, ein Windschutz muss 70 % der Burg 15 s halten
5. **Gerecht teilen** – ein Strahl, zwei Becher

## Demo-Szenen

1. **Kaskade** – Becher laufen über die niedrigere Kante in den nächsten über
2. **Trichter: Wasser gegen Sand** – gleiche Engstelle, Wasser läuft druckabhängig, Sand rieselt gleichmäßig und bildet einen Kegel
3. **Kommunizierende Röhren** – verschieden breite und schiefe Kammern, überall gleicher Pegel
4. **Dammbruch** – Tor öffnet sich, die Flutwelle läuft durchs Tal und kommt zur Ruhe
5. **Schleuse** – Tore öffnen und schließen im Wechsel, das Boot wird gehoben und gesenkt

## Physik in Kürze

- Positionsbasierte Dynamik mit 8 Teilschritten pro Bild.
- Wasser–Wasser: *Double Density Relaxation* (Clavet et al. 2005), Druck aus lokaler Dichte, nur abstoßend. Harte Kugelkontakte allein verklemmen im Ruhezustand wie ein Glas (Pegel gleichen sich nicht aus, Bälle bleiben unter Wasser).
- Viskosität (XSPH) als einstellbare Dämpfung: Schwappen klingt ab, das Becken wird still.
- Sand: harte Kontakte mit Coulomb-Reibung, Schock-Propagation und Vorstabilisierung (stabile Haufen).
- Bälle im Wasser: Auftrieb nach Archimedes aus dem eingetauchten Anteil plus Strömungswiderstand; Rollen mit Haftreibung.

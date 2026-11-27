# DJ-MiX

Mixtape-App im Browser: **https://adam1001es.github.io/DJ-MiX/**

Zwei Videos oder Songs laden – die App nimmt nur den Ton. Zuerst kommt Song A, dann eine eigene Beat-Brücke, dann Song B. Am Ende bekommst du den Mix als MP3.

## Prinzip

- **Die Songs werden nie schneller oder langsamer.** A und B laufen immer im Originaltempo.
- **Keine Überlappung.** Zwischen A und B baut die App einen eigenen Übergangs-Beat. Nur darin gleitet das Tempo von A zu B.
- **Reihenfolge fest:** A → Brücke → B.

## Die Formel

Die App analysiert die letzten ~32 Sekunden von A und die ersten ~32 Sekunden von B: Tempo, Beat-Raster (an der Bassdrum), Takt-Eins (Kick, Energie- und Akkordwechsel), Tonart (Chroma, Camelot) und Energie pro Takt (Outro, Intro, Drop).

Daraus baut sie die Brücke:

1. **Schnitt auf der Eins:** A endet auf einer Takt-Eins (vor einem leisen Outro, falls vorhanden). B startet auf einer Takt-Eins – bei ruhigem Intro direkt am Drop.
2. **A-Loop:** Der letzte Takt von A läuft als Loop weiter und wird mit Hochpass ausgeblendet.
3. **Eigener Beat:** Drums, Bass und Akkorde. Der Stil passt zum Tempo (Hip-Hop, Club, Rock) und wechselt in der Mitte vom Stil von A zum Stil von B.
4. **Tempo-Gleiten:** nur innerhalb der Brücke, weich von BPM A zu BPM B.
5. **Harmonie:** Akkorde aus der Tonart von A, dann über eine Kadenz (Dominante) in die Tonart von B.
6. **B-Teaser:** Im letzten Takt stottert der Anfang von B hoch (1 → ½ → ¼ → ⅛ Schlag) mit Snare-Roll und Riser, dann ein halber Schlag Pause, und B startet auf der Eins.
7. **Lautstärke:** Die Brücke wird an A und B angepasst, der Mix wird gegen Übersteuern abgesichert.

Länge: Auto (2, 4 oder 8 Takte je nach Tempo-Abstand) oder fest wählbar.

## Export

- **MP3** (192 kbit/s) speichern oder über „Teilen“ weitergeben.
- „Ganzer Mix“ oder „Nur Übergang“ (16 s A + Brücke + 16 s B).

## Hinweise

- iPhone: Lautlos-Schalter ausschalten, sonst kein Ton beim Vorhören.
- Alles läuft im Browser, nichts wird hochgeladen.

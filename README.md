# DJ-MiX

DJ-Übergangs-App im Browser: **https://adam1001es.github.io/DJ-MiX/**

Zwei Videos oder Songs laden – die App nimmt nur den Ton. Der Mixer analysiert das Ende von Song A und den Anfang von Song B und baut daraus einen Übergang, der musikalisch passt.

## Aufbau

- **Oben: Deck A und Deck B.** Song oder Video laden (MP3, M4A, WAV, MP4, MOV, WebM), mit „Von“ und „Bis“ zuschneiden. Stille am Anfang und Ende wird automatisch abgeschnitten.
- **Unten: der Mixer.** Er zeigt den Übergangs-Plan als Zeitleiste und führt ihn aus – auf Knopfdruck oder automatisch am Ende von A.

## Die Formel

Der Mixer analysiert die letzten ~32 Sekunden von A und die ersten ~32 Sekunden von B:

1. **Tempo (BPM)** über Onset-Autokorrelation, fein nachjustiert auf 0,02 BPM.
2. **Beat-Raster** an der Bassdrum ausgerichtet.
3. **Takt-Eins (Downbeat)** aus Kick-Anteil, Energiewechseln und Akkordwechseln (Chroma).
4. **Tonart** per Chroma und Krumhansl-Profil, angezeigt im Camelot-System (z. B. 8A).
5. **Energie pro Takt:** wird das Outro von A leiser? Hat B ein ruhiges Intro und einen Drop?

Daraus entscheidet „Auto“:

| Situation | Übergang |
|---|---|
| Tempo fast gleich (≤ 6 %), Tonarten passen | **Langer Blend** 4–8 Takte, Bass-Tausch auf der Eins, Mitten getrennt |
| Tempo fast gleich, Tonarten beißen sich | **Bass-Swap** 2 Takte, A wird dünn gefiltert |
| Tempo 6–16 % auseinander | **Filter-Blend** mit resonantem Hochpass, B wird angeglichen und gleitet danach zurück |
| Tempo weit auseinander (z. B. Rap 90 → Pop 128), A läuft voll | **Build & Drop**: Loop-Roll ½ → ¼ → ⅛ Schlag mit Riser, halber Schlag Stille, B fällt mit seinem Drop auf die Eins |
| Tempo weit auseinander, Outro von A wird leiser | **Echo-Out** im Takt, B setzt einen Takt später ein |

Der Übergang endet genau auf einer Takt-Eins am „Bis“-Punkt von A. Bei Blends liegt das Intro von B unter A, sodass sein Drop kommt, wenn A weg ist.

Manuell wählbar: Blend, Filter, Echo-Out, Build & Drop, Bremse, Cut.

## Hinweise

- Tempo-Angleichen verändert auch die Tonhöhe, wie am Plattenspieler. Der Mixer rechnet das bei der Tonart mit ein.
- iPhone: Lautlos-Schalter ausschalten, sonst kommt kein Ton.
- Alles läuft im Browser, nichts wird hochgeladen.

# Mathe-Spiele 🎮

Sammlung von **Vorlagen für HTML5-Mathe-Spiele**: Jede Datei ist ein komplettes, offline lauffähiges Spiel und zugleich eine Schablone für beliebige Mathe-Themen. Die Aufgaben sind nicht fest eincodiert, sondern werden von **Aufgaben-Generatoren** erzeugt, mit Distraktoren, die typische Schülerfehler abdecken. Ein neues Thema ist meist nur ein neuer Generator-Eintrag.

Zielgruppe: Schüler:innen (aktuell v. a. Klasse 5–10) und Patenkinder. Einsatz im Unterricht, auf dem Handy, offline im Browser.

## 🎯 Direktlinks zu den Spielen

| Spiel | Version | Direktlink |
|---|---|---|
| Mathe-Racer (Retrowave) | Retrowave, Stand 15.11.2026 | [Mathe_Racer_Retrowave.html](Mathe_Racer_Retrowave.html) |
| Rechen-Schlange | V2, Stand 15.11.2026 | [Rechen_Schlange_V2.html](Rechen_Schlange_V2.html) |

Zum Testen: Datei im Link öffnen → `Raw`-Ansicht → herunterladen und im Browser öffnen.

## Die Vorlagen

### 🏁 Mathe-Racer (Retrowave)
[`Mathe_Racer_Retrowave.html`](Mathe_Racer_Retrowave.html) – Rennspiel im Retrowave-Look (Pink `#ff4fd8`, Cyan `#35e0ff`, Violett `#B18CD9`): Richtige Antworten geben Tempo, Fehler kosten Zeit, mit Partikeln, Flash und Shake.

**Themen:** `pvs` (Punkt vor Stricht), `units` (Größen & Einheiten), `bruch` (Brüche), `prozent`, `terme` (Terme), `pytta` (Satz des Pythagoras), `zufall` (Wahrscheinlichkeit), `alles` (Mix).

**Anpassen:** Im `<script>`-Block das Objekt `TRACKS` erweitern. Ein Thema ist eine Funktion, die `q(aufgabentext, ergebnis)` zurückgibt:

```js
const TRACKS = {
  // … bestehende Themen …
  meinThema: () => {
    const a = rnd(9) + 2;
    return q(`Ableitung von x^${a} = ?`, a);
  }
};
```

`alles` nimmt neue Themen automatisch in den Mix auf (dort `pick([...])`-Liste ergänzen).

### 🐍 Rechen-Schlange
[`Rechen_Schlange_V2.html`](Rechen_Schlange_V2.html) – Snake im 3B1B-Design mit großem Touch-D-Pad, kompatibel zur Racer-Farbpalette. Richtige Antwort = Futter (wachsen), falsche Antwort = Leben verlieren. Dient außerdem als **Struktur-/Steuerungs-Vorlage** für weitere Apps.

**Themen:** `add1` (bis 20), `add2` (bis 100), `mul` (Einmaleins), `div`, `mix`, `percent` (Prozent & Größen), weitere Generatoren mit kompetitiven Distraktoren.

**Anpassen:** analog über das Objekt `MODES` im `<script>`-Block.

## Neue Spiele aus Vorlagen ableiten

1. Datei kopieren und im `TRACKS`/`MODES`-Objekt die Themen auf das Zielthema umrüsten
2. Titel, Wortmarke und Fragen-Format anpassen; Design-Tokens (CSS-`:root`) unverändert lassen
3. Offline-Test im Browser (Desktop + Handy)

## Design-Konventionen (verbindlich für alle Spiele)

- Hintergrund `#0a0c10`, Flächen `#0e1218` / `#12161d`, Text linksbündig, keine Glows außer Spielfeld
- Retrowave-Akzente: Pink `#ff4fd8`, Cyan `#35e0ff`, Violett `#B18CD9`; Basis-Variablen aus `Rechen_Schlange_V2.html`
- Dezente Creepster-Wortmarke in Braun `#644533`, Akzent Teal `#5CD0B3`
- Touch-optimiert (D-Pad bzw. große Buttons)
- Keine externen Loader/CDNs (Offline-Fähigkeit)

## Verwandte Projekte

- [Lernkarten](https://github.com/schreeckkai/Lernkarten) – JSON-Kartenstapel und Lernkarten-Trainer (GitHub Pages)
- [Mathe_Apps](https://github.com/schreeckkai/Mathe_Apps) – kleine Apps für den Unterricht
- [komplexe-geogebra-apps](https://github.com/schreeckkai/komplexe-geogebra-apps) – interaktive GeoGebra-Lernapps

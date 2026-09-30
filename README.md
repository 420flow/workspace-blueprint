# KI-Workspace-Blueprint

Ein kompletter Workspace für die Arbeit mit KI-Agenten in einer einzigen Datei: Ordnerstruktur, Regeln, vier Skills (Hub-Update, Feierabend, Posteingang verarbeiten, Steckbrief) und Vorlagen. Drei Bereiche: **Beruflich** mit je einem Ordner für Hauptjob, Nebenjob, eigene Firma und berufliche Vorhaben, **Persönlich** mit Lebensbereichen wie Finanzen, Gesundheit, Wohnen und Verwaltung, dazu ein **Wissens-Wiki**. Ein Agent mit Dateizugriff (Claude Code, Codex, Antigravity) packt die Datei aus, stellt dir ein paar Fragen und richtet alles ein.

Von **Finn Ole Behrends** · [LinkedIn](https://www.linkedin.com/in/finn-behrends) · Lizenz [CC BY 4.0](LICENSE) · aktuelle Version **1.0** vom 2026-09-30

## So richtest du ihn ein

1. [`BLUEPRINT.md` herunterladen](https://github.com/420flow/workspace-blueprint/raw/main/BLUEPRINT.md). Der Dateiname muss `BLUEPRINT.md` bleiben.
2. Einen leeren Ordner anlegen, zum Beispiel `~/Desktop/<dein-vorname>`, und die Datei hineinlegen. Nicht in einen Cloud-Ordner deines Arbeitgebers.
3. Den Ordner in Claude Code, Codex oder Antigravity öffnen und diesen Prompt eingeben:

> Lies BLUEPRINT.md vollständig und richte meinen Workspace genau so ein, wie es dort im Abschnitt „Anweisung an den Agenten“ steht. Schreibe die Dateien nicht selbst, sondern nutze den Extraktor aus der Datei. Stell mir danach die Fragen aus dem Abschnitt „Einrichtung“ einzeln mit nummerierten Antwortmöglichkeiten und fülle die Platzhalter. Zum Schluss zeig mir ERSTE-SCHRITTE.md.

Vorher den Abschnitt „Bevor du loslegst“ oben in der Datei lesen: Datenschutz, eigene Firma, Haftung. Dauer rund 15 Minuten.

## Echtheit prüfen

Die Prüfsumme der aktuellen Fassung steht in [`SHA256SUMS`](SHA256SUMS). Auf dem Mac im Ordner der Datei prüfen:

```bash
shasum -a 256 BLUEPRINT.md
```

Stimmt die Zahl nicht überein, ist die Datei verändert. Dann nicht verwenden, sondern hier neu herunterladen.

## Weitergeben

Gern. Am besten den Link auf dieses Repo, dann bekommt jeder die aktuelle Fassung. Wer die Datei selbst weitergibt oder anpasst, lässt Namen, Lizenzlink und den Hinweis „ohne Gewähr“ drin und kennzeichnet Änderungen.

## Versionen

| Version | Datum | Änderung |
|---|---|---|
| 1.0 | 2026-09-30 | Erste öffentliche Fassung |

## Ohne Gewähr

Nutzung auf eigenes Risiko, ohne Support. Rückmeldungen und Verbesserungsideen gern über [LinkedIn](https://www.linkedin.com/in/finn-behrends).

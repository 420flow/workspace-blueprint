# KI-Workspace-Blueprint

Ein kompletter Workspace für die Arbeit mit KI-Agenten in einer einzigen Datei: Ordnerstruktur, Regeln, vier Skills (Hub-Update, Feierabend, Posteingang verarbeiten, Steckbrief) und Vorlagen. Drei Bereiche: **Beruflich** mit je einem Ordner für Hauptjob, Nebenjob, eigene Firma und berufliche Vorhaben, **Persönlich** mit Lebensbereichen wie Finanzen, Gesundheit, Wohnen und Verwaltung, dazu ein **Wissens-Wiki**. Ein Agent mit Dateizugriff (Claude Code, Codex, Antigravity) packt die Datei aus, stellt dir ein paar Fragen und richtet alles ein.

Von **Finn Ole Behrends** · [LinkedIn](https://www.linkedin.com/in/finn-behrends) · Lizenz [CC BY 4.0](LICENSE) · aktuelle Version **1.2** vom 2026-09-30

## So richtest du ihn ein

1. Leg einen leeren Ordner an, zum Beispiel `~/Desktop/<dein-vorname>`. Nicht in einen Cloud-Ordner deines Arbeitgebers, der Workspace gehört dir.
2. Öffne den Ordner in Claude Code, Codex oder Antigravity.
3. Gib diesen Prompt ein:

> Prüfe zuerst mit `ls -A`, ob dieser Ordner leer ist. Einträge mit einem Punkt am Anfang zählen nicht, und öffne keine vorhandenen Dateien. Ist er nicht leer, lade nichts herunter und ändere nichts, sondern erklär mir, wie ich einen neuen leeren Ordner anlege und dort neu starte. Ist er leer, lade mit `curl -fsSLO https://raw.githubusercontent.com/420flow/workspace-blueprint/main/BLUEPRINT.md` die Datei BLUEPRINT.md herunter, lies sie vollständig und richte meinen Workspace genau so ein, wie es dort im Abschnitt „Anweisung an den Agenten“ steht.

Der Agent prüft zuerst, ob der Ordner wirklich leer ist, und fragt dann, ob er den Download ausführen darf: erlauben. Danach stellt er dir ein paar Fragen, Dauer rund 15 Minuten. Lies vorher den Abschnitt [„Bevor du loslegst“](BLUEPRINT.md#bevor-du-loslegst): Datenschutz, eigene Firma, Haftung.

Voraussetzung: ein Mac mit `python3`. Fragt macOS nach den Befehlszeilen-Entwicklerwerkzeugen, installieren und den Prompt erneut eingeben. Auf Windows den Ordner in Git Bash oder WSL öffnen.

**Falls der Agent nichts herunterladen darf** (Codex blockiert das oft): [`BLUEPRINT.md` herunterladen](https://github.com/420flow/workspace-blueprint/raw/main/BLUEPRINT.md), in den leeren Ordner legen (der Name muss `BLUEPRINT.md` bleiben) und den Prompt aus dem Kopf der Datei eingeben.

## Echtheit prüfen

Die Prüfsumme der aktuellen Fassung steht in [`SHA256SUMS`](SHA256SUMS). Auf dem Mac im Ordner der Datei prüfen:

```bash
shasum -a 256 BLUEPRINT.md
```

Stimmt die Zahl nicht überein, ist die Datei verändert. Dann nicht verwenden, sondern hier neu herunterladen.

## Weitergeben

Gern. Am besten den Prompt von oben oder den Link auf dieses Repo, dann bekommt jeder die aktuelle Fassung direkt von hier. Wer die Datei selbst weitergibt oder anpasst, lässt Namen, Lizenzlink und den Hinweis „ohne Gewähr“ drin und kennzeichnet Änderungen.

## Versionen

| Version | Datum | Änderung |
|---|---|---|
| 1.2 | 2026-09-30 | Agent prüft vor allem anderen, ob der Ordner leer ist und ob er in einem Cloud-Speicher liegt; neutrale Beispiele statt realer Anbieter |
| 1.1 | 2026-09-30 | Link auf dieses Repo als offizielle Fassung im Kopf und im eingerichteten Workspace, Echtheitsprüfung über `SHA256SUMS` |
| 1.0 | 2026-09-30 | Erste öffentliche Fassung |

## Ohne Gewähr

Nutzung auf eigenes Risiko, ohne Support. Rückmeldungen und Verbesserungsideen gern über [LinkedIn](https://www.linkedin.com/in/finn-behrends).

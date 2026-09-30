# KI-Workspace-Blueprint: dein Second Brain für KI-Agenten

*An AI second brain workspace for Claude Code, Codex and Antigravity, set up from a single file. In German.*

Ein Second Brain, mit dem dein KI-Agent arbeitet: ein kompletter Workspace in einer einzigen Datei. Ein Agent mit Dateizugriff (Claude Code, Codex, Antigravity) packt sie aus, stellt dir ein paar Fragen und richtet Ordner, Regeln, Skills und Vorlagen für Beruf, Privates und ein eigenes Wissens-Wiki ein. Danach weiß dein Agent in jeder neuen Sitzung, wo was liegt, und macht dort weiter, wo du aufgehört hast. Notizen, Projekte, Dokumente und Wissen liegen als einfache Markdown-Dateien bei dir, nicht in einer App.

Von **Finn Ole Behrends** · [LinkedIn](https://www.linkedin.com/in/finn-behrends) · Lizenz [CC BY 4.0](LICENSE) · aktuelle Version **1.4** vom 2026-09-30 · auf Deutsch

## Schnellstart

1. Leg einen neuen, leeren Ordner an, zum Beispiel `Mein Workspace` auf dem Schreibtisch. Nicht in einen Cloud-Ordner deines Arbeitgebers, der Workspace gehört dir.
2. Öffne den Ordner in Claude Code, Codex oder Antigravity. ChatGPT oder Claude im Browser reichen nicht, das Programm braucht Zugriff auf den Ordner.
3. Gib diesen Prompt ein:

> Prüfe zuerst mit `ls -A`, ob dieser Ordner leer ist. Einträge mit einem Punkt am Anfang zählen nicht, und öffne keine vorhandenen Dateien. Ist er nicht leer, lade nichts herunter und ändere nichts, sondern erklär mir, wie ich einen neuen leeren Ordner anlege und dort neu starte. Ist er leer, lade mit `curl -fsSLO https://raw.githubusercontent.com/420flow/workspace-blueprint/main/BLUEPRINT.md` die Datei BLUEPRINT.md herunter, lies sie vollständig und richte meinen Workspace genau so ein, wie es dort im Abschnitt „Anweisung an den Agenten“ steht.

4. Fragt der Agent, ob er den Download ausführen darf: erlauben. Danach beantwortest du seine Fragen. Dauer rund 15 Minuten.

Lies vorher den Abschnitt [„Bevor du loslegst“](BLUEPRINT.md#bevor-du-loslegst) in der Datei: Datenschutz, eigene Firma, Haftung.

**Falls der Agent nichts herunterladen darf** (Codex blockiert das oft): [`BLUEPRINT.md` herunterladen](https://github.com/420flow/workspace-blueprint/raw/main/BLUEPRINT.md), in den leeren Ordner legen (der Name muss `BLUEPRINT.md` bleiben) und den Prompt aus dem Kopf der Datei eingeben.

## Voraussetzungen

- **Ein KI-Programm mit Ordnerzugriff:** Claude Code (auch im Code-Bereich der Claude-App), Codex oder Antigravity.
- **Mac:** `python3` ist dabei. Fragt macOS beim ersten Mal nach den Befehlszeilen-Entwicklerwerkzeugen: installieren, dann den Prompt erneut eingeben.
- **Windows:**
  1. Python 3 von [python.org](https://www.python.org/downloads/) installieren und dabei den Haken bei „Add python.exe to PATH“ setzen.
  2. Am zuverlässigsten läuft es mit Claude Code, das Git Bash mitbringt. Codex am besten über WSL.
  3. In der reinen PowerShell übersetzt der Agent die Befehle selbst.
- Kein GitHub-Konto nötig, keine weitere Installation.

## Was du bekommst

```text
Mein Workspace/
├── AGENTS.md, CLAUDE.md, GEMINI.md   Regeln und Übersicht für deinen Agenten
├── README.md, CONTEXT.md, AUFGABEN.md, PROFIL.md, GOTCHAS.md
├── posteingang/                      hier legst du alles Neue ab
├── beruflich/<bereich>/              je Job, Firma oder Vorhaben ein Ordner, darin Projekte
├── persoenlich/<thema>/              Finanzen, Gesundheit, Wohnen, Verwaltung und mehr
├── wissen/                           dein Wissens-Wiki mit Quellen und Themen
└── .agents/skills/                   vier Skills, Kopie für Claude Code in .claude/skills/
```

Im Alltag sagst du deinem Agenten nur noch:

| Du sagst | Der Agent |
|---|---|
| „Posteingang verarbeiten“ | sortiert Chats, Notizen, Transkripte und Dokumente aus `posteingang/` in die Struktur, trägt Aufgaben und Fristen ein |
| „Hub Update“ | hält nach einer Sitzung fest, was passiert ist, damit jede neue Sitzung dort weitermacht |
| „Feierabend“ | Tagesabschluss: wie Hub Update, dazu eine kurze Tageszusammenfassung und ein Blick auf Ordnung und Posteingang |
| „Steckbrief anlegen“ | fragt einmal deine Anbieter, Verträge und Ärzte ab, damit Dokumente richtig landen |

Alles sind einfache Markdown-Dateien in deinem Ordner. Du kannst den Workspace mit jedem dieser Programme öffnen und das Programm jederzeit wechseln.

## Datenschutz und Sicherheit

- **Alles bleibt in deinem Ordner.** Kein Konto, keine Cloud, keine Telemetrie.
- **Der Extraktor** ist ein kurzes Python-Programm in der Datei. Er greift nicht aufs Internet zu, schreibt nur in deinen Ordner und löscht sich danach selbst. Dein Agent prüft ihn vor dem Ausführen.
- **Was dein Agent liest, verarbeitet der Anbieter deines KI-Programms.** Schalte in dessen Einstellungen die Nutzung fürs Training ab. Daten von Kunden, Mitarbeitenden oder Bewerbern nur mit einem Vertrag zur Auftragsverarbeitung (AVV) mit dem Anbieter.
- **Sicherheitslücke gefunden?** Bitte vertraulich melden, siehe [SECURITY.md](SECURITY.md).

## Häufige Probleme

| Meldung | Lösung |
|---|---|
| „Der Ordner ist nicht leer“ | Neuen, leeren Ordner anlegen, dort das Programm öffnen und den Prompt erneut eingeben. Den alten Ordner musst du nicht leeren. |
| „Python wurde nicht gefunden“ oder der Microsoft Store öffnet sich | Python 3 von python.org installieren (Haken bei „Add python.exe to PATH“), Programm neu starten, Prompt erneut eingeben. |
| macOS fragt nach Entwicklerwerkzeugen | Installieren, dann den Prompt erneut eingeben. |
| „Der Ordner .agents darf hier nicht angelegt werden“ | Das Programm läuft in einer Sandbox. In Claude Code den Berechtigungsmodus auf Fragen oder Auto stellen und neu starten. |
| Codex darf nichts herunterladen | Datei über den Link oben selbst herunterladen, in den Ordner legen, Prompt aus dem Kopf der Datei eingeben. |
| „Prüfsumme falsch“ | Die Datei ist beschädigt oder verändert. Hier neu herunterladen. |

## Aktualisieren

Neue Versionen erneuern die Skills und Vorlagen. Deine Notizen, Projekte und Dokumente bleiben unberührt, eigene Änderungen an den Skills werden überschrieben. Im Workspace-Ordner diesen Prompt eingeben:

> Lade mit `curl -fsSLO https://raw.githubusercontent.com/420flow/workspace-blueprint/main/BLUEPRINT.md` die aktuelle BLUEPRINT.md in diesen Ordner. Prüfe den Extraktor wie in Schritt 1 der Datei beschrieben, speichere ihn unverändert als extract.py und führe ihn mit `--update` aus. Verschiebe BLUEPRINT.md danach nach posteingang/archiv/ und hänge die Version an den Dateinamen an. Sag mir die neue Version aus .agents/blueprint-version.txt.

## Echtheit prüfen

Die Prüfsumme der aktuellen Fassung steht in [`SHA256SUMS`](SHA256SUMS). Im Ordner der Datei:

- Mac: `shasum -a 256 BLUEPRINT.md`
- Windows (PowerShell): `Get-FileHash BLUEPRINT.md`

Stimmt die Zahl nicht überein (Groß- und Kleinschreibung egal), ist die Datei verändert. Dann nicht verwenden, sondern hier neu herunterladen.

## Weitergeben und Lizenz

Weitergeben ist ausdrücklich erwünscht, am besten den Prompt von oben oder den Link auf dieses Repo. Dann bekommt jeder die aktuelle Fassung direkt von hier. Lizenz [CC BY 4.0](LICENSE): Nutzen, anpassen und weitergeben, auch in Firmen, solange Name, Lizenzlink und der Hinweis „ohne Gewähr“ erhalten bleiben und Änderungen gekennzeichnet sind.

## Versionen

| Version | Datum | Änderung |
|---|---|---|
| 1.4 | 2026-09-30 | Windows: Anleitung für Python, PowerShell und Git Bash; Extraktor verträgt UTF-16 und `desktop.ini` |
| 1.3 | 2026-09-30 | Standard bei den beruflichen Bereichen ist nur noch der Hauptjob |
| 1.2 | 2026-09-30 | Agent prüft vor allem anderen, ob der Ordner leer ist und ob er in einem Cloud-Speicher liegt; neutrale Beispiele |
| 1.1 | 2026-09-30 | Link auf dieses Repo als offizielle Fassung, Echtheitsprüfung über `SHA256SUMS` |
| 1.0 | 2026-09-30 | Erste öffentliche Fassung |

## Ohne Gewähr

Nutzung auf eigenes Risiko, ohne Support. Rückmeldungen und Verbesserungsideen gern über [LinkedIn](https://www.linkedin.com/in/finn-behrends).

# GitHub Actions

Dieses Repository dient als Vorlage für GitHub Actions Workflows. Es bietet eine einfache Struktur und nützliche Beispiele, um schnell mit GitHub Actions zu starten.

## Inhalt

- [Überblick](#überblick)
- [Verwendung](#verwendung)
- [Struktur](#struktur)
- [Anpassung](#anpassung)
- [Beispiele](#beispiele)
- [Ressourcen](#ressourcen)
- [Lizenz](#lizenz)

## Überblick 

GitHub Actions ermöglichen es dir, automatisierte Workflows direkt in deinem GitHub Repository zu erstellen und auszuführen. Diese Vorlage zeigt grundlegende Beispiele und kann leicht angepasst werden, um auf spezifische Bedürfnisse einzugehen.

## Verwendung

Um diese Vorlage zu verwenden, folge diesen Schritten:

1. **Repository klonen**:
   ```bash
   git clone https://github.com/Mockerman/GitActions.git
   ```
2. **In das Repository wechseln**:
   ```bash
   cd github-actions-template
   ```
3. **Workflow-Datei anpassen**: Bearbeite die Datei `.github/workflows/main.yml` nach deinen Bedürfnissen.
4. **Änderungen committen und pushen**:
   ```bash
   git add .
   git commit -m "Anpassungen am Workflow"
   git push origin main
   ```

## Struktur

Dieses Repository enthält die folgende Struktur:

```plaintext
.github/
└── workflows/
    └── main.yml
README.md
```

- **`.github/workflows/main.yml`**: Die Hauptworkflow-Datei, die die Schritte definiert, die GitHub Actions ausführt.
- **`README.md`**: Diese Datei, die Informationen über die Verwendung des Repositories bietet.

## Anpassung

Die Vorlage enthält mehrere Beispielschritte, die du leicht anpassen kannst:

```yaml
name: GitHub Actions Demo
on: [push]

jobs:
  Erkunde-GitHub-Actions:
    runs-on: ubuntu-latest
    steps:
      - name: Repository-Code auschecken
        uses: actions/checkout@v4

      - name: Trigger-Ereignis ausgeben
        run: echo "🎉 Der Job wurde automatisch durch ein ${{ github.event_name }} Ereignis ausgelöst."

      - name: Runner-Betriebssystem ausgeben
        run: echo "🐧 Dieser Job läuft nun auf einem ${{ runner.os }} Server, der von GitHub gehostet wird!"

      - name: Branch-Name und Repository ausgeben
        run: echo "🔎 Der Name deines Branches ist ${{ github.ref }} und dein Repository ist ${{ github.repository }}."

      - name: Klonen des Repository bestätigen
        run: echo "💡 Das ${{ github.repository }} Repository wurde auf den Runner geklont."

      - name: Runner vorbereiten
        run: echo "🖥️ Der Workflow ist jetzt bereit, deinen Code auf dem Runner zu testen."

      - name: Dateien im Repository auflisten
        run: ls ${{ github.workspace }}

      - name: Job-Status ausgeben
        run: echo "🍏 Der Status dieses Jobs ist ${{ job.status }}."

      - name: Abhängigkeiten installieren (optional)
        run: |
          if [ -f package.json ]; then
            npm install
          elif [ -f requirements.txt ]; then
            pip install -r requirements.txt
          fi
```

### Beispiele

Hier sind einige gängige Anpassungen, die du vornehmen kannst:

- **Zusätzliche Schritte hinzufügen**:
  ```yaml
  - name: Führe Tests aus
    run: npm test
  ```

- **Umgebung variablen setzen**:
  ```yaml
  env:
    NODE_ENV: production
  ```

- **Andere Runner verwenden**:
  ```yaml
  runs-on: windows-latest
  ```

## Ressourcen

- [GitHub Actions Dokumentation](https://docs.github.com/en/actions)
- [Weitere GitHub Actions Beispiele](https://github.com/actions)

## Lizenz

Dieses Projekt steht unter der MIT-Lizenz. Siehe die [LICENSE](LICENSE) Datei für weitere Details.
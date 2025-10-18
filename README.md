# SPD Langenselbold Jubiläums-Quiz

Interaktives Quiz zum 135-jährigen Jubiläum des SPD-Ortsvereins Langenselbold (1890–2025).

## Features

- 20 Fragen zur Geschichte der SPD Langenselbold
- Sofortiges Feedback mit Erklärungen
- Randomisierte Fragen und Antworten für Wiederspielbarkeit
- Live-Score-Anzeige
- Konfetti-Effekt bei richtigen Antworten
- Teilbare Ergebnis-Kachel als PNG-Download
- Responsive Design für Desktop und Mobile
- Druckfunktion

## Live Demo

Die Anwendung ist live unter: `https://[IHR-USERNAME].github.io/SPD-Quiz/`

## Lokale Entwicklung

1. Repository klonen:
```bash
git clone https://github.com/[IHR-USERNAME]/SPD-Quiz.git
cd SPD-Quiz
```

2. HTML-Datei in einem Browser öffnen:
```bash
# Windows
start index.html

# macOS
open index.html

# Linux
xdg-open index.html
```

Oder einen lokalen Webserver starten:
```bash
# Python 3
python -m http.server 8000

# Node.js
npx http-server
```

## Deployment auf GitHub Pages

### Erste Einrichtung

1. Erstellen Sie ein Repository auf GitHub:
   - Gehen Sie zu https://github.com/new
   - Repository-Name: `SPD-Quiz`
   - Sichtbarkeit: Public (für GitHub Pages)

2. Pushen Sie den Code:
```bash
git init
git add .
git commit -m "Initial commit: SPD Langenselbold Quiz"
git branch -M main
git remote add origin https://github.com/[IHR-USERNAME]/SPD-Quiz.git
git push -u origin main
```

3. GitHub Pages aktivieren:
   - Gehen Sie zu Repository → Settings → Pages
   - Source: Deploy from a branch
   - Branch: `main` / `(root)`
   - Klicken Sie auf "Save"

4. Nach ca. 1-2 Minuten ist die Seite live unter:
   `https://[IHR-USERNAME].github.io/SPD-Quiz/`

### Updates deployen

Nach Änderungen:
```bash
git add .
git commit -m "Beschreibung der Änderungen"
git push
```

GitHub Pages wird automatisch aktualisiert.

## Projektstruktur

```
SPD-Quiz/
├── index.html                  # Haupt-Quiz-Anwendung
├── assets/
│   └── images/
│       └── spd-ls-logo.svg     # SPD Langenselbold Logo
├── .nojekyll                   # GitHub Pages Konfiguration
└── README.md                   # Diese Datei
```

## Anpassungen

### Logo ersetzen

Ersetzen Sie `assets/images/spd-ls-logo.svg` mit Ihrem Logo (PNG, JPG oder SVG).

### Fragen bearbeiten

Öffnen Sie `index.html` und suchen Sie nach `const QUESTIONS = [`.

Format für Fragen:
```javascript
{
  id: 1,
  text: "Ihre Frage?",
  answers: [
    {text: "Antwort 1", correct: false, explain: "Erklärung 1"},
    {text: "Antwort 2", correct: true, explain: "Erklärung 2"},
    {text: "Antwort 3", correct: false, explain: "Erklärung 3"},
    {text: "Antwort 4", correct: false, explain: "Erklärung 4"}
  ]
}
```

### Design anpassen

CSS-Variablen in `index.html` (Zeilen 8-18):
```css
:root {
  --spd-red: #E3000F;  /* Hauptfarbe */
  --ink: #131516;       /* Textfarbe */
  --bg: #fbfbfb;        /* Hintergrund */
  /* ... weitere Farben */
}
```

## Browser-Kompatibilität

- Chrome/Edge (empfohlen)
- Firefox
- Safari
- Mobile Browser (iOS Safari, Chrome Mobile)

## Technologien

- Reines HTML5 / CSS3 / JavaScript (ES6+)
- Keine externen Abhängigkeiten
- Canvas API für Social-Share-Kacheln
- Native Web Share API

## Lizenz

© 2025 SPD Langenselbold. Alle Rechte vorbehalten.

## Support

Bei Fragen oder Problemen öffnen Sie ein Issue auf GitHub.

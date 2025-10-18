# WordPress Embedding Guide

Einfache Anleitung zum Einbetten des SPD Langenselbold Quiz in deine WordPress-Website.

## Voraussetzungen

1. GitHub Pages ist aktiviert für dein Repository
2. Das Quiz ist live unter: `https://cbraunfi.github.io/SPD135Quiz/`
3. Deine WordPress-Seite erlaubt Custom HTML

## Empfohlene Lösung: Feste Höhe mit responsive Staffelung

Diese Lösung ist einfach, robust und funktioniert ohne externe Skripte.

### Copy-Paste Code für WordPress:

```html
<style>
  #spd-quiz-iframe { height: 1800px; }
  @media (max-width: 1024px) { #spd-quiz-iframe { height: 1650px; } }
  @media (max-width: 640px)  { #spd-quiz-iframe { height: 1500px; } }
</style>

<div style="max-width:980px;margin:0 auto">
  <iframe
    id="spd-quiz-iframe"
    title="SPD Langenselbold Jubiläums-Quiz"
    src="https://cbraunfi.github.io/SPD135Quiz/"
    style="width:100%;border:0;border-radius:16px;box-shadow:0 8px 24px rgba(0,0,0,.08);"
    loading="lazy"
    allow="clipboard-read; clipboard-write; web-share; fullscreen"
  ></iframe>
</div>
```

### Höhen-Staffelung:
- **Desktop (>1024px)**: 1800px Höhe
- **Tablet (641-1024px)**: 1650px Höhe
- **Mobile (≤640px)**: 1500px Höhe

**Tipp:** Falls unten etwas abgeschnitten ist, erhöhe die Höhe auf 1900px (Zeile 2).

## So fügst du es in WordPress ein:

### Mit Gutenberg (Block Editor):
1. Öffne deine Seite im Editor
2. Klicke auf **+** (Block hinzufügen)
3. Suche nach **"Custom HTML"** oder **"Benutzerdefiniertes HTML"**
4. Füge den Code oben ein
5. **Vorschau** anzeigen und testen
6. **Veröffentlichen**

### Mit Classic Editor:
1. Öffne deine Seite im Editor
2. Wechsle zum **Text**-Tab (nicht Visual)
3. Füge den Code oben ein
4. Wechsle zurück zu **Visual** für Vorschau
5. **Veröffentlichen**

### Mit Page Builder (Elementor, Divi, etc.):
1. Füge ein **HTML Widget** oder **Code Block** hinzu
2. Füge den Code oben ein
3. Speichern und Vorschau

## Alternative: Einfacher iframe ohne responsive Staffelung

Falls du keine CSS-Anpassungen möchtest:

```html
<div style="max-width:980px;margin:0 auto">
  <iframe
    title="SPD Langenselbold Jubiläums-Quiz"
    src="https://cbraunfi.github.io/SPD135Quiz/"
    style="width:100%;height:1800px;border:0;border-radius:16px;box-shadow:0 8px 24px rgba(0,0,0,.08);"
    loading="lazy"
    allow="clipboard-read; clipboard-write; fullscreen"
  ></iframe>
</div>
```

## Fehlerbehebung

### iframe wird nicht angezeigt
- Prüfe, ob dein WordPress-Theme/Security-Plugin iframes blockiert
- Füge `cbraunfi.github.io` zu deiner Allowlist hinzu

### Höhe passt nicht
- Erhöhe die Höhenwerte in den CSS-Regeln
- Für Desktop: erhöhe von 1800px auf 1900-2000px
- Für Mobile: erhöhe von 1500px auf 1600-1700px

### HTTPS-Warnung
- GitHub Pages nutzt HTTPS
- Stelle sicher, dass auch deine WordPress-Seite HTTPS nutzt

## Customizing

### Andere maximale Breite:
Ändere `max-width:980px` in Zeile 7 auf deinen gewünschten Wert.

### Ohne Schatten:
Entferne `box-shadow:0 8px 24px rgba(0,0,0,.08);` aus dem Style.

### Ohne abgerundete Ecken:
Entferne `border-radius:16px;` aus dem Style.

## Support

Bei Fragen oder Problemen öffne ein Issue auf GitHub:
https://github.com/CBraunFI/SPD135Quiz/issues

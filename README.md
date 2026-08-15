# Da Giabatta Ristoro — Website

Statische One-Pager-Website für das italienische Café / Feinkostgeschäft
**Da Giabatta Ristoro**, Lousbergstraße 66, 52072 Aachen.

Lokale Kopie des Claude-Artifacts
`https://claude.ai/code/artifact/f5fde1e8-1c3c-4cb4-810e-5604ca980a3a`,
entpackt am 2026-08-15. Alle Assets sind lokal — **keine externen Requests
zur Laufzeit**, kein Build-Step, kein Backend.

## Struktur

```
index.html                  # die komplette Seite (Markup + 3 inline <style>-Blöcke)
assets/js/dc-runtime.js     # Claude-Design-Composer-Runtime (rendert <x-dc>)
assets/js/image-slot.js     # <image-slot> Custom Element (Bild-Platzhalter)
assets/fonts/*.woff2        # Karla + Libre Caslon Text (latin / latin-ext)
vendor/react*.min.js        # React 18.3.1 UMD, von der Runtime nachgeladen
```

`index.html` beginnt mit einem injizierten `window.__resources`-Mapping, das
die Runtime auf die lokalen React-Dateien in `vendor/` zeigen lässt. Ohne das
würde sie React von unpkg.com holen (Original-Verhalten im Artifact-Bundle).

## Lokal ansehen

`index.html` einfach im Browser öffnen — funktioniert auch per Doppelklick
(`file://`, getestet). Für einen realistischeren Test:

```bash
npx serve .          # oder: python -m http.server 8000
```

## Inhalt der Seite

Hero → Öffnungszeiten → Feinkost aus Italien (Antipasti, Formaggi, Salumi,
Pasta & Sughi, Olio & Aceto, Vino) → Caffè & Frisches vom Tag →
Events & private Feiern → Besuch / Anfahrt → Footer.

## Bekannte offene Punkte

- **Keine echten Bilder.** Alle Bildflächen sind leere `<image-slot>`-
  Platzhalter (gestrichelte Kästen mit Beschriftung, z. B. „Antipasti-Auswahl
  in Gläsern"). Echte Fotos müssen noch eingesetzt werden.
- **Kein Formular.** „Anfrage senden" ist ein `mailto:info@daristoro.de` —
  Event-Anfragen laufen also über den Mail-Client des Besuchers.
- Der Facebook-Link zeigt auf `https://facebook.com` (keine konkrete Seite).
- Unten rechts blendet die Runtime ein „Made with Claude Design"-Badge ein.

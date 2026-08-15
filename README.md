# Da Giabatta Ristoro — Website

Statische One-Pager-Website für das italienische Café / Feinkostgeschäft
**Da Giabatta Ristoro**, Lousbergstraße 66, 52072 Aachen.

Reines HTML + CSS: **kein JavaScript, kein Build-Step, kein Backend.**
Alle Assets liegen im Repo — zur Laufzeit gehen keine Requests an fremde
Server (die einzigen externen URLs sind die Links zu Google Maps, Instagram
und Facebook, die der Besucher selbst anklickt).

## Struktur

```
index.html            # die komplette Seite (Markup + Styles inline)
assets/fonts/*.woff2  # Karla + Libre Caslon Text (latin / latin-ext)
```

## Lokal ansehen

`index.html` im Browser öffnen — Doppelklick genügt. Alternativ:

```bash
npx serve .          # oder: python -m http.server 8000
```

## Deployment

GitHub Pages, Quelle `main` / root. **Jeder Push auf `main` geht live** —
keine Workflow-Datei nötig, Pages baut direkt aus dem Branch.

## Inhalt der Seite

Hero → Öffnungszeiten → Feinkost aus Italien (Antipasti, Formaggi, Salumi,
Pasta & Sughi, Olio & Aceto, Vino) → Caffè & Frisches vom Tag →
Events & private Feiern → Besuch / Anfahrt → Footer.

## Offene Punkte

- **Keine echten Bilder.** Alle 16 Bildflächen sind Platzhalter (gestrichelter
  Rahmen + Beschreibung, z. B. „Antipasti-Auswahl in Gläsern"). Zum Einsetzen
  eines Fotos den jeweiligen `<div class="img-ph" id="…">` durch ein
  `<img>` mit denselben Maßen ersetzen.
- **Kein `<title>`**, keine Meta-Description, keine OG-Tags, kein
  strukturiertes Datenmarkup (`LocalBusiness`). Für die Auffindbarkeit bei
  Google ist das der wichtigste offene Punkt.
- **Kein Formular.** „Anfrage senden" ist ein `mailto:info@daristoro.de`.
- Der Facebook-Link zeigt auf `https://facebook.com` (keine konkrete Seite).

# Da Giabatta Ristoro — Website

> **Projekt pausiert.** `index.html` zeigt aktuell nur einen Pausen-Hinweis
> (`noindex`). Die vollständige Seite liegt in der Git-Historie im Commit
> `a486fb5` und kommt mit
> `git checkout a486fb5 -- index.html` zurück.
> Die restliche Doku unten beschreibt diese vollständige Seite.

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
assets/img/*.jpg      # 15 Beispielbilder (CC0/Public Domain, siehe IMAGE-CREDITS.md)
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

## Bilder austauschen

Die 15 Bilder sind **Beispielbilder aus gemeinfreien Quellen**, keine Fotos des
echten Ladens (Nachweise in `IMAGE-CREDITS.md`). Zum Austauschen genügt es, die
Datei unter `assets/img/<id>.jpg` durch ein eigenes Foto **mit gleichem Namen**
zu ersetzen — das Markup muss nicht angefasst werden. Die IDs entsprechen den
Bildflächen (`hero-bg`, `feinkost-antipasti`, `caffe-img`, `insta-1` …).

Sinnvolle Größen: Hero ~1800 px breit, Karten ~900 px, Instagram-Kacheln ~600 px.

## Offene Punkte

- **`location-map` ist weiterhin ein Platzhalter** (gestrichelter Rahmen). Dort
  gehört ein Kartenausschnitt oder ein Foto der Lousbergstraße hin — ein
  beliebiges fremdes Straßenfoto wäre an dieser Stelle irreführend.
- **Kein `<title>`**, keine Meta-Description, keine OG-Tags, kein
  strukturiertes Datenmarkup (`LocalBusiness`). Für die Auffindbarkeit bei
  Google ist das der wichtigste offene Punkt.
- **Kein Formular.** „Anfrage senden" ist ein `mailto:info@daristoro.de`.
- Der Facebook-Link zeigt auf `https://facebook.com` (keine konkrete Seite).

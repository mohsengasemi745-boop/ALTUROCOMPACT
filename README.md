# ALTURO COMPACT SRL — Website

Site oficial de prezentare pentru ALTURO COMPACT SRL, centru de colectare și
valorificare a deșeurilor feroase și neferoase din Reșița, jud. Caraș-Severin.

Site static (HTML/CSS/JS), fără build step, fără dependențe — gata de publicat.

## Structura proiectului

```
/
├── index.html              Pagina principală (conținut + structură)
├── css/
│   └── style.css           Toate stilurile site-ului
├── js/
│   └── script.js           Interacțiuni: loader, scroll-reveal, contoare animate, meniu mobil
├── assets/
│   ├── images/             Fotografii din activitate (galerie)
│   ├── icons/               (rezervat pentru iconițe suplimentare)
│   └── logo/                Logo-ul companiei (SVG + PNG, mai multe variante)
├── favicon.ico              Iconița site-ului (tab browser)
└── README.md                 Acest fișier
```

## Fișiere logo disponibile (`assets/logo/`)

| Fișier | Descriere | Utilizare recomandată |
|---|---|---|
| `logo-mark.svg` | Doar simbolul, o culoare, fundal transparent | Print, gravură, folosire pe un singur ton |
| `logo-badge.svg` | Simbol + fundal verde rotunjit | Favicon, avatar social media |
| `logo-badge.png` | Variantă PNG a badge-ului, rezoluție mare | Cazuri unde SVG nu e acceptat |
| `logo-mark.png` | Simbol transparent, PNG | Suprapunere peste imagini |
| `logo-mark-white.png` | Simbol alb, transparent | Fundaluri închise (ex. mașini, uniforme) |

Logo-ul folosit direct în site (în meniu și footer) este inline în `index.html`
pentru performanță maximă (fără cerere de rețea suplimentară) — fișierele din
`assets/logo/` sunt copiile "master", pregătite de export pentru materiale
tipărite, camioane sau rețele sociale.

## Rulare locală

Nu necesită instalare. Deschide `index.html` direct în browser, sau pornește
un server local simplu:

```bash
# Python
python3 -m http.server 8080

# Node
npx serve .
```

Apoi accesează `http://localhost:8080`.

## Deploy pe Vercel

1. Urcă folderul într-un repository GitHub (vezi mai jos).
2. Pe [vercel.com](https://vercel.com) → **New Project** → selectează repo-ul.
3. Framework Preset: **Other** (site static, fără build command).
4. Output Directory: lasă gol / `.` (rădăcina proiectului).
5. Deploy — gata.

## Deploy pe GitHub Pages (alternativă)

1. Creează un repository nou pe GitHub și încarcă toate fișierele păstrând
   structura de foldere.
2. Settings → Pages → Source: branch `main`, folder `/ (root)`.
3. Site-ul va fi disponibil la `https://<user>.github.io/<repo>/`.

## Ce trebuie actualizat manual

- Telefon, adresă, program: în `index.html`, secțiunea `#contact` și `#despre`.
- Link Facebook: căutați `facebook.com/alturo.compact.srl` în `index.html`.
- Fotografii galerie: înlocuiți fișierele din `assets/images/` păstrând
  aceleași nume, sau actualizați `src="assets/images/..."` din `index.html`.

## Note tehnice

- Toate căile din `index.html` sunt relative — proiectul funcționează identic
  indiferent de subfolder-ul în care este publicat.
- Imaginile din galerie au fost optimizate pentru web (redimensionate,
  comprimate JPEG progresiv) pentru încărcare rapidă.
- Site-ul respectă `prefers-reduced-motion` — animațiile se dezactivează
  automat pentru utilizatorii care au această preferință activă în sistem.

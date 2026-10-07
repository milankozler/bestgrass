# BestGrass – web

Statický web pro BestGrass (Scoba plus s.r.o., Podbořany): renovace trávníků, automatická závlaha, půjčovna strojů, chytrá zahrada na Loxone.

## Nasazení na Netlify

1. Netlify → **Add new site → Import an existing project** → vybrat tento repozitář.
2. Build command: *(prázdné)*, Publish directory: `/` (kořen repozitáře). Žádný build není potřeba.
3. Po prvním nasazení zkontrolovat **Site configuration → Forms**: Netlify při nasazení sám najde 4 formuláře
   (`poptavka-travnik`, `poptavka-zavlaha`, `rezervace-pujcovna`, `kontakt`).
4. **Forms → Form notifications** → přidat e-mail `technik@scobaplus.cz` (nebo jiný), kam mají chodit odeslané poptávky.

Formuláře posílají i fotky (max. 4, před odesláním se v prohlížeči zmenší na 1600 px, cca 300–400 kB každá).
Bezplatná úroveň Netlify Forms má limit na počet odeslání a objem příloh za měsíc – zkontrolovat v ceníku Netlify.

## Struktura

- `index.html` – celý web (jedna stránka s kotvami)
- `soukromi.html` – ochrana osobních údajů (doplnit IČO a sídlo)
- `dekujeme.html` – poděkování po odeslání formuláře bez JavaScriptu
- `img/` – fotografie (zmenšené na web, max. 1600 px)
- `netlify.toml` – cache pro obrázky a bezpečnostní hlavičky
- `robots.txt`, `favicon.svg`

## Co doplnit před ostrým spuštěním

- IČO a sídlo firmy do patičky a do `soukromi.html`
- potvrdit otevírací dobu (Po–pá 8–17) a slib „odpovíme do 24 hodin“
- vlastní doménu v Netlify (Domain management) a poté `og:image` v `<head>` s absolutní adresou

# Plakatgenerator – Tønsberg kommune

Lag plakater (A4) og skjermversjoner (16:9) etter kommunens grafiske profil.

## Innhold

| Fil / mappe | Hva det er |
|---|---|
| `index.html` | Selve generatoren. **Ikke rediger denne for hånd** – den er ferdigbygd. |
| `bilder/` | Bildebanken. Legg bilder her. |
| `bilder/bildeinfo.csv` | Valgfri tilleggsinfo om bildene. |
| `verktoy/bildebank.py` | Skript som gjør bildene klare for nettsiden. Kjøres automatisk. |
| `.github/workflows/publiser.yml` | Automatisk publisering til GitHub Pages. |

## Oppsett (én gang)

1. Last opp alle filene til repoet (behold mappestrukturen, også `.github`).
2. Gå til **Settings → Pages** og velg **Source: GitHub Actions**.
3. Under **Actions** ser du jobben «Publiser plakatgenerator». Når den er grønn (1–2 min), er siden ute.

## Legge til bilder

Last opp bildene til mappen `bilder/`. Det er alt.
Publiseringen kjører automatisk, lager nettversjoner (maks 2600 px) og miniatyrer, og oppdaterer bildebanken.
Bruk helst bilder på minst 2500 px på lengste side, så de holder til trykk.

Fjerne et bilde: slett det fra `bilder/`.

## Tilleggsinfo (valgfritt) – `bilder/bildeinfo.csv`

Kan redigeres i Excel (lagre som CSV, semikolon). Én rad per bilde, bare filnavnet er påkrevd:

| Kolonne | Eksempel | Brukes til |
|---|---|---|
| `fil` | `AdobeStock_76053361.jpg` | Hvilket bilde raden gjelder |
| `beskrivelse` | `Forelder og barn ved brygga` | Vises i bildebanken og gjør bildet søkbart |
| `fotograf` | `Ola Nordmann` | Vises i bildebanken |
| `utloper` | `2027-12-31` | Bildet forsvinner automatisk etter denne datoen (bruksrett) |
| `fokus_x`, `fokus_y` | `50`, `40` | Standard utsnitt i prosent (0 = venstre/topp, 100 = høyre/bunn) |

## Rullering

For at de samme bildene ikke skal brukes hele tiden:

- Hver måned «hviler» omtrent en tredjedel av bildene (gjelder når banken har minst 9 bilder). De kommer tilbake måneden etter.
- Rekkefølgen stokkes på nytt hver dag.
- Hver bruker ser merket «Du brukte dette …» på bilder de selv har lastet ned plakater med (lagres bare i egen nettleser).

Hvilende bilder kan likevel hentes fram via lenken nederst i bildebanken.

## Merk

- Siden er offentlig. Bilder i `bilder/` må være klarert for publisering.
- Originalbildene ligger i repoet, men bare nedskalerte kopier publiseres på nettsiden.
- Åpnes `index.html` direkte fra disk, virker alt unntatt bildebanken.

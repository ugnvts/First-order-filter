# First order filter

PMS (Picking) „Number of first orders“ filtro prototipai: rodomos tik pirmųjų N užsakymų (pagal short order ID) užduotys. Skirta surinkimo centrams su ribota konsolidacijos vieta.

## Failai

| Failas | Kas tai | Nuoroda |
|---|---|---|
| `index.html` | Prototipų apvalkalas: ekrano ir varianto skirtukai | – |
| `puslapiai/unfinished-picking-tasks.html` | Unfinished picking tasks su Short order ID stulpeliu ir filtru „Number of first orders“. Variantas pasirenkamas `#A` / `#B` | `#a`, `#b` |
| `scripts/build-pages.py` | Sugeneruoja `docs/` (GitHub Pages svetainę) | – |
| `docs/` | Vieša svetainė – **ranka netaisyti**, generuojama skriptu | – |

### Variantai

- **A · Active filters row** – mygtukas atsiranda aktyvių filtrų juostos dešinėje, kai pasirinkti Delivery date ir Wave. Nuėmus kurį nors iš jų, filtras išvalomas.
- **B · Last filter** – mygtukas visada paskutinis filtrų eilėje. Delivery date ir Wave nebūtini; be jų imami visi nebaigti užsakymai.

Abiejuose: užsakymai rikiuojami pagal pristatymo datą, tada short order ID; imami pirmieji N; kiti filtrai tik slepia tų užsakymų užduotis. Duomenys išgalvoti.

## Vieša nuoroda

- Naujausia: https://ugnvts.github.io/First-order-filter/ (A: `#a`, B: `#b`)
- Užšaldytos versijos: https://ugnvts.github.io/First-order-filter/versijos/

## Kaip atnaujinti

1. Taisyk failus `puslapiai/`.
2. Naujas variantas: failas `puslapiai/` + eilutė `PAGES` sąraše `index.html`. Pervadinus variantą seną id įrašyk į `ALIAS`.
3. Atnaujink svetainę: `python3 scripts/build-pages.py`
4. Užšaldyk versiją (review, patvirtinimams): `python3 scripts/build-pages.py --release "Kas šioje versijoje"` → `docs/versijos/YYYY-MM-DD/`. Užšaldytos versijos niekada nesikeičia.
5. Commit, tada GitHub Desktop → **Push origin**.

Saugykla vieša – konfidencialius failus laikyk `archyvas/` (į git nepatenka).

# Airport Navi — prototype

Interactive prototype of **Airport Navi**, a web app passengers open by scanning a QR poster at NAIA (Manila). No install, no account. Navigation is the core: enter a flight number and get walked to the gate, or to your baggage carousel when you land.

**Live demo:** https://msys-ai-research.github.io/airport-navi/
**Business Portal (concept):** https://msys-ai-research.github.io/airport-navi/portal.html

> Prototype only. Flights, bag status, positions, fares, drivers and partner services are simulated. Maps are schematic (not to scale) and built from public guides, not official plans from NNIC, NAIA's operator.

## What you can try

- **Find my gate:** enter a sample departure (e.g. `PR 102`) → flight card → *Take me there* → full-screen map with turn-by-turn steps.
- **Arrivals:** switch Home to *Arriving* and enter `PR 101` → carousel and bag status → *Guide me to Carousel 5* walks you from the arrival bridge through immigration and down to baggage claim, then offers toilets, exit & rides, money and SIM.
- **Get a ride:** compare Grab, JoyRide and the airport taxi queue (illustrative fares and waits), book, see the driver and plate, then *Start walking to Pick-up Bay 4*.
- **Scan a QR code:** tap *Scan* on Home or the top card on *Where are you?*; demo posters set your exact spot and facing, and can switch terminal.
- **Gate change:** open the **Demo** tab on the right edge → *Gate change*. The new route draws in, the old one fades and the new ETA is shown.
- **Terminal switch:** pick `PR 300` (Terminal 1) while on the Terminal 3 map and accept the prompt; the map swaps and your flight stays.
- **Map:** drag to pan, scroll or pinch to zoom, *+ / − / fit* buttons; *walk ▶* moves the blue dot; the Demo panel's phone compass shows the facing cone and "Turn around" cue.
- **Domestic vs international (T3):** gates across the glass partition show a "no walking route" state instead of a path.
- **Concierge, amenities, shops & lounges, travel forms, services (mini programs).**
- **Business Portal:** linked from the Demo panel. Blueprint scanner, tenant & amenity CMS with approvals, promotions & banners, foot-traffic & merchant analytics, integrations & mini-program registry.

### Sample flights

| Flight | Direction | Terminal | Gate / Carousel | Notes |
| --- | --- | --- | --- | --- |
| PR 102 | To Singapore | T3 | Gate 112 | International, south-east finger |
| Z2 330 | To Tokyo Narita | T3 | Gate 104 | International |
| 5J 453 | To Davao | T3 | Gate 118 | Domestic side |
| PR 2811 | To Iloilo | T3 | Gate 132 | Bus gate, ground level, delayed |
| PR 300 | To Hong Kong | T1 | Gate 11 | West hub |
| UO 553 | To Hong Kong | T1 | Gate 2 | Lower level via stairs |
| PR 101 | From Singapore | T3 | Carousel 5 | Landed, bags unloading |
| UO 552 | From Hong Kong | T1 | Carousel 3 | Landed, waiting for first bags |
| Z2 331 | From Tokyo Narita | T3 | Carousel 7 | En route |

Clock is fixed at 13:02, 28 Sep. Flight data mimics the Cirium Flight Status format; bag status is sample data that would come from NAIA's baggage system.

## How it's built

- `index.html` (passenger app) and `portal.html` (Business Portal) are each one self-contained file — vanilla JS, no build step, no dependencies. Font: DM Sans (Google Fonts).
- Terminal maps: corridor graph per terminal with zones (domestic / international / arriving / landside), one-way checkpoints (immigration, customs), level changes (stairs, escalators, lifts) and shortest-path routing; directions are generated from the path. Arrivals maps show Level 2 and Level 1 unfolded on one sheet.
- `.nojekyll` makes GitHub Pages serve the files as-is.

## Run locally

Open `index.html` in any browser. No server needed.

## Publish on GitHub Pages

Repository **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)`**. The site appears at the live demo URL above within a minute or two.

## Credits

- Sample photos from [Unsplash](https://unsplash.com), loaded from their public links (Unsplash License): Spencer Plouzek, Alexander Schimmeck, rustam burkhanov, Max Harlynking, Haberdoedas, Eiliv Aceron, Long Chung, Soyoung HAN, National Cancer Institute, Tim Mossholder, N1CE, Global Residence Index, Pic Kaca, Javier Cañada.
- Terminal layouts from public airside guides ([ittekuru.com](https://ittekuru.com) T1/T3 guides, manila-airport.net, Wikipedia). Gate order in T3 international, carousel and pick-up bay positions, and shop positions are placeholders until official plans are available.
- Airline, lounge and ride-hail names are used for illustration only; this project is not affiliated with NNIC, MIAA, any airline or any ride-hail company.

# Airport Navi — prototype

Interactive prototype of **Airport Navi**, a web app passengers open by scanning a QR poster at NAIA (Manila). No install, no account. Navigation is the core: enter a flight number and get walked to the gate.

**Live demo:** https://msys-ai-research.github.io/airport-navi/

> Prototype only. Flights, positions and partner services are simulated. Maps are schematic (not to scale) and built from public guides, not official MIAA plans.

## What you can try

- **Find my gate:** enter a sample flight (e.g. `PR 102`) → flight card → *Take me there* → full-screen map with turn-by-turn steps.
- **Gate change:** open the **Demo** tab on the right edge → *Gate change*. The alert sheet appears and the route updates.
- **Where am I?:** pick a landmark or switch terminal (T1 / T3); every route and walk time updates.
- **Search button (centre):** pre-filled with your gate; also finds toilets, food, lounges, charging.
- **Domestic vs international (T3):** gates across the glass partition show a "no walking route" state instead of a path.
- **Concierge, amenities, shops & lounges, travel forms, services (mini programs).**

### Sample flights

| Flight | To | Terminal · Gate | Notes |
| --- | --- | --- | --- |
| PR 102 | Singapore | T3 · 112 | International, south-east finger |
| Z2 330 | Tokyo Narita | T3 · 104 | International |
| 5J 453 | Davao | T3 · 118 | Domestic side |
| PR 2811 | Iloilo | T3 · 132 | Bus gate, ground level, delayed |
| PR 300 | Hong Kong | T1 · 11 | West hub |
| UO 553 | Hong Kong | T1 · 2 | Lower level via stairs |

Clock is fixed at 13:02, 28 Sep. Flight data mimics the Cirium Flight Status format.

## How it's built

- One self-contained `index.html` — vanilla JS, no build step, no dependencies. Font: DM Sans (Google Fonts).
- Terminal maps: corridor graph per terminal with zones (domestic / international), level changes (stairs, escalators, lifts) and shortest-path routing; directions are generated from the path.
- `.nojekyll` makes GitHub Pages serve the file as-is.

## Run locally

Open `index.html` in any browser. No server needed.

## Publish on GitHub Pages

Repository **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)`**. The site appears at the live demo URL above within a minute or two.

## Credits

- Sample photos from [Unsplash](https://unsplash.com), loaded from their public links (Unsplash License): Spencer Plouzek, Alexander Schimmeck, rustam burkhanov, Max Harlynking, Haberdoedas, Eiliv Aceron, Long Chung, Soyoung HAN, National Cancer Institute, Tim Mossholder, N1CE, Global Residence Index, Pic Kaca, Javier Cañada.
- Terminal layouts from public airside guides ([ittekuru.com](https://ittekuru.com) T1/T3 guides, manila-airport.net, Wikipedia). Gate order in T3 international and shop positions are placeholders until official plans are available.
- Airline codes and lounge names are used for illustration only; this project is not affiliated with MIAA or any airline.

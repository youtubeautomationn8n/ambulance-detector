# 🚨 Green Corridor AI — Ambulance Detector (Demo Prototype)

Highway camera watches traffic → AI detects the ambulance → picks the emptiest lane → LED board orders that lane cleared.

## Try it
- **Simulation mode:** press 🚨 Send Ambulance — watch siren early-warning, flash-pattern confirmation, lane scoring, corridor clearing.
- **Live camera mode:** 🎥 Switch to Live Camera on your phone, point at flashing red/blue lights (e.g. an ambulance-lights video on a laptop screen).

## How detection works
- **Flash pattern:** per-cell red-minus-blue oscillation @ ~5Hz — no ML model needed. Steady brake lights don't trigger it.
- **Siren:** mic → FFT, detects the 700→1500 Hz wail sweep. Hears around corners before the camera sees anything.
- **Lane choice:** score = vehicles in lane + 0.4 × distance from ambulance lane. Fewest people disturbed wins.

100% in-browser, zero servers, zero cost. Just deploy `index.html` (Vercel / GitHub Pages).

# GoPada Astro Suite — Divisional Charts & Rectification

A single-file, browser-based tool that pairs a **birth-time rectification dashboard**
(eight standard Parashara divisional charts that update live as you nudge the birth time)
with a **Varga Explorer** — a learning tool for visualising *any* division (D1–D300) as a
continuous Parivritti (cyclical) loop.

No installation, no server, no account. Open the HTML file and it runs.

---

## Why this tool exists

Two everyday needs in divisional (varga) work sit together here:

1. **Rectification is a live problem.** When you're refining a birth time, you want to watch
   the *lagna* — and every varga's lagna — shift as you adjust the clock, so you can lock onto
   the moment where the D9, D10, D60 lagnas line up with known life events. This tool recomputes
   all eight charts instantly on every ±minute nudge.
2. **Divisions are easier understood as a cycle.** The Varga Explorer treats any Dn as a loop of
   equal slices around the zodiac (the Parivritti method), so you can *see* how a division carves
   each sign — how wide each slice is, where the D1 boundaries fall, and which slice any longitude
   lands in — for divisions all the way up to D300.

Rectification for real charts; the Explorer for learning and research. The Help dialog states this
split plainly.

---

## The two modules

### 🧭 Rectification Dashboard
Paste a chart and a birth time, and get eight divisional charts side by side, each drawn as a
**South Indian rasi chart**:

**D1** (Rasi) · **D9** (Navamsa) · **D10** (Dasamsa) · **D12** (Dwadasamsa) ·
**D4** (Chaturthamsa) · **D7** (Saptamsa) · **D24** (Siddhamsa) · **D60** (Shashtyamsa)

- **Live time adjustment** — **−1 / +1 minute** buttons, a manual minute field (fractions allowed),
  and **Reset**. One minute of clock time shifts the lagna ~0.25°, and every chart redraws instantly.
- **Lagna-only shift** — planets are held (they barely move in a few minutes) while the lagna moves,
  which is exactly what rectification needs.
- **Planetary longitudes table** — each planet's D1 longitude alongside its D9 / D10 / D60 placements.
- Charts are computed with **traditional Parashara varga rules**.

### 🔭 Varga Explorer
A research/learning surface for any single division:

- **Any Dn from 1 to 300** — type the number; the tool shows **total parts** and the **span** of
  each slice (e.g. D9 → 108 parts of 3°20′).
- **Cyclical sequence strip** — a scrollable ribbon of the first 60 slices in the Parivritti loop,
  colour-coded by sign, with the D1 (30°) boundaries marked in degrees.
- **Placement Calculator** — enter a longitude (`145.5` or `Le 25 30`) and it tells you which
  slice/sign that position falls in, and the slice's exact arc.
- **Reference table** — every slice's arc and sign, in a **List** view or a per-sign **Grid** view.
- **Clean-division warning** — flags divisions whose span doesn't land on whole seconds.

### Extras
- **360° Zodiac Divider** — a quick utility: `360 ÷ n` to see the arc of any n-fold division.
- **Print View** — prints the dashboard, or the Explorer's reference table, cleanly.
- **Help** — an in-app explanation of both modules.

---

## How to use it

### For rectification
1. **Open** `GPP_Divisional_charts-v1.html` (a sample chart is preloaded).
2. On the **Rectification Dashboard** tab, set the **Name** and **Birth Time**, and paste the
   chart into **Chart Data** (JHora "Body / Longitude" format). Click **Generate Charts**.
3. Use **−1 / +1 Min**, the minute box, or **Reset** to move the birth time. Watch the D1–D60
   lagnas shift and settle the time against known events.
4. Check the **Planetary Longitudes** table and **Print View** when done.

### For exploring a division
1. Switch to the **Varga Explorer** tab.
2. Type a division number (1–300). Read the total parts and span, scan the **cyclical strip**,
   and use the **Placement Calculator** to test specific longitudes.
3. Toggle the reference table between **List** and **Grid**, and **Print View** to export it.

---

## Input format

Paste a JHora-style export — a body name followed by `DD Sign MM' SS"`:

```
Body              Longitude        Nakshatra Pada Rasi Navamsa
Lagna             27 Cp 17' 52.24" Dhan      2    Cp   Vi
Sun - MK/PiK      13 Ta 38' 46.76" Rohi      2    Ta   Ta
Moon - BK         16 Cn 48' 02.35" Asre      1    Cn   Sg
...
```

Notes:
- Sign codes are the two-letter set (`Ar Ta … Pi`); tags like ` (R)` and karaka labels are tolerated.
- A **Lagna** line is required (it's the point the rectification shift acts on).

---

## A note on method

- The **Rectification Dashboard** uses classical **Parashara** varga rules (e.g. the D9
  fire/earth/air/water starting signs, the D10 odd/even rule, and so on), and applies the birth-time
  shift to the **lagna only**.
- The **Varga Explorer** deliberately uses the **Parivritti (cyclical)** method — a uniform loop of
  equal slices — as a visual/learning model, which is *not* identical to every classical varga's
  traditional starting-sign rule. Use the dashboard for chart-accurate vargas and the Explorer to
  understand the geometry of a division.

---

## Tech & privacy

- **One HTML file.** No build step. The core rectification and Explorer logic is plain, embedded JavaScript.
- **Runs in the browser**; your chart data is processed locally and never uploaded.
- **No persistence** — nothing is saved between sessions; use **Print View** to keep a copy.
- The file declares an import map for some front-end libraries (React, d3, lucide) via CDN; the
  rectification and Explorer features themselves run on embedded vanilla JS.

---

## License

Released under the **MIT License**.

## Credits

Built and maintained by **AstroGaami**.

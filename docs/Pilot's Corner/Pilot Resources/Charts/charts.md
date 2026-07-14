# How to Read Aviation Charts

> A guide for VATSIM pilots and controllers covering the most common chart types used in real-world and simulated IFR operations.

---

## Table of Contents

1. [Types of Aviation Charts](#types-of-aviation-charts)
2. [SID Charts (Standard Instrument Departure)](#1-sid-charts)
3. [STAR Charts (Standard Terminal Arrival Route)](#2-star-charts)
4. [Approach Charts](#3-approach-charts)
5. [Airport/Ground Charts](#4-airportground-charts)
6. [En-Route Charts](#5-en-route-charts)
7. [Common Symbols & Conventions](#common-symbols--conventions)
8. [Reading a Chart Step-by-Step](#reading-a-chart-step-by-step)
9. [Chart Providers](#chart-providers)

---

## Types of Aviation Charts

| Chart Type | Purpose | Who Uses It Most |
|---|---|---|
| SID | Departure routing from airport | Pilots, Delivery/Ground ATC |
| STAR | Arrival routing to an airport area | Pilots, Approach/Centre ATC |
| Approach (IAP) | Final approach to a runway | Pilots, Approach/Tower ATC |
| Airport/Ground | Taxiways, runways, aprons | Pilots, Ground/Tower ATC |
| En-Route (Low/High) | Cruise navigation on airways | Pilots, Centre ATC |

---

## 1. SID Charts

A **Standard Instrument Departure (SID)** is a pre-planned IFR routing from the departure end of a runway to a fix or waypoint where the en-route phase begins.

### Anatomy of a SID Chart

```
┌─────────────────────────────────────────────────────────┐
│  HEADER BLOCK                                           │
│  Airport name / ICAO | Chart name | Chart index number  │
│  Effective date | Variation | Transition altitude       │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│  PLAN VIEW (top-down map)                               │
│  • Airport symbol at centre                             │
│  • Departure runways highlighted                        │
│  • Route lines with arrows showing direction of travel  │
│  • Waypoints (named fixes) along the route              │
│  • Minimum Obstacle Clearance Altitude (MOCA) arcs      │
│  • Terrain or obstacle shading if relevant              │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│  TEXTUAL/TABULAR SECTION                                │
│  • Takeoff minimums (visibility, ceiling)               │
│  • Climb gradients required                             │
│  • Routing instructions per runway                      │
│  • Transition routes to specific en-route fixes         │
└─────────────────────────────────────────────────────────┘
```

### Key Things to Read on a SID

**Name and applicability** — the SID name includes a code and a number, e.g. `RAGUL3A`. The letter suffix often denotes a revision. Check it applies to your departure runway.

**Climb gradient** — many SIDs have a required climb gradient (e.g. 400 ft/NM). If your aircraft cannot meet this, you may not be able to use the SID or will need to advise ATC.

**Altitude constraints** — shown on waypoints as:
- `FL150` = cross AT that altitude
- `+FL110` = cross AT OR ABOVE
- `-8000` = cross AT OR BELOW
- `8000A` and `FL130B` together = cross BETWEEN those altitudes

**Speed restrictions** — often shown as `250KT` or `210KT` at specific waypoints. In a lot of Africa, you may see `MAX 210KT`, which is a Speed limit point. If you are unable to fly slower than 210, you must advise ATC and fly your slowest speed. On the side of a typical arrival chart, you may see a MAX below a certain altitude. Be advised that this is usually a suggestion and may be overrid by ATC (unless you are in USA where 250 is common below 10,000 ft.)

**Transitions** — a SID may have multiple named transitions that branch off to different en-route fixes. ATC will specify which one to fly, e.g. `MERIT2A BOLNO TRANSITION`.

---

## 2. STAR Charts

A **Standard Terminal Arrival Route (STAR)** is a pre-planned IFR routing from an en-route fix down to the initial approach fix (IAF) or a point where you are vectored for the approach.

### Anatomy of a STAR Chart

The layout mirrors the SID, but the direction of flight is inbound to the airport. Key differences:

**Entry transitions** — multiple fixes where aircraft can join the STAR from different directions (east, west, etc.). ATC assigns the transition, e.g. `NEEKO2A NEEKO TRANSITION`.

**Altitude constraints** — same notation as SIDs. On a STAR these are typically descend-to altitudes and are critical for vertical spacing with other traffic.

**Speed restrictions** — very common on STARs, especially near busy airports. Expect `250KT` or lower at various points. In South Africa, speed restrictions are the following: 250KTs within 50 DME of the airport and 210KTs within 15DME of the airport.

**Published holding patterns** — some STARs have holding fixes where ATC can stack traffic. These are shown as racetrack ovals on the chart.

**The IAF (Initial Approach Fix)** — where the STAR ends and the approach begins. Usually shown as a named waypoint with a thicker symbol.

### STAR vs Radar Vectors

On VATSIM and in real operations, ATC may issue radar vectors instead of the full published STAR, or may shorten ("direct to") a waypoint mid-STAR. Always listen to ATC instructions — published procedures are the default, but ATC clearances take precedence.

---

## 3. Approach Charts

Approach charts (formally Instrument Approach Procedures, or IAPs) are the most information-dense charts you will encounter. They describe the lateral and vertical path to land on a specific runway.

### Types of Approaches

| Type | Lateral Guidance | Vertical Guidance | Notes |
|---|---|---|---|
| ILS | Localiser (LOC) | Glideslope | Most precise; used to low minimums |
| LPV | GNSS (GPS) | SBAS glidepath | GPS precision approach; similar to ILS, common in the US and Europe |
| VOR | VOR radial | None (or step-down) | Older; non-precision |
| NDB | NDB bearing | None | Rare; mostly legacy |
| RNAV (GPS) | GNSS/RNP | None (LNAV) or with SBAS (LPV/LNAV+V) | Common at smaller airports |
| Visual | ATC / pilot | Pilot | Not a published instrument approach |

### Anatomy of an Approach Chart

```
┌──────────────────────────────────────────────────────────────────┐
│  HEADER BLOCK                                                    │
│  Airport ICAO | Runway | Approach type | Chart number            │
│  Transition altitude | MSA (Minimum Safe Altitude) circle        │
└──────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────┐
│  PLAN VIEW (top-down)                                            │
│  • Inbound course/localiser/VOR radial                          │
│  • IAF, IF (Intermediate Fix), FAF (Final Approach Fix)          │
│  • Missed Approach Point (MAP) and missed approach routing       │
│  • Minimum Safe Altitude (MSA) arcs by sector                   │
│  • Significant terrain/obstacles                                 │
└──────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────┐
│  PROFILE VIEW (side elevation)                                   │
│  • Glideslope or step-down altitudes along the approach path     │
│  • FAF altitude | Decision Altitude or MDA                       │
│  • Threshold Crossing Height (TCH)                               │
│  • Missed approach climb gradient                                │
└──────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────┐
│  MINIMUMS TABLE                                                  │
│  • By aircraft category (A/B/C/D) and approach type              │
│  • DA/H or MDA/H (Decision Altitude/Height or Minimum Descent    │
│    Altitude/Height)                                              │
│  • Required Visibility (RVR or Horizontal in  Meters             │
└──────────────────────────────────────────────────────────────────┘
```

### The Minimums Table in Detail

```
CAT     │     ILS/LOC     │   CIRCLE   │
────────┼─────────────────┼────────────┤
A       │ DA(H) 287 (200) │ MDA 460    │
B       │ DA(H) 287 (200) │ MDA 500    │
C       │ DA(H) 287 (200) │ MDA 560    │
D       │ DA(H) 287 (200) │ MDA 660    │
```

- **DA (Decision Altitude)** — altitude at which you must have visual references or execute the missed approach. Used for precision approaches (ILS, LPV).
- **MDA (Minimum Descent Altitude)** — lowest altitude you may descend to without visual reference. You continue at MDA until the MAP, then go missed. Used for non-precision approaches.
- **The number in brackets** (e.g. `(200)`) is the height relative to the airport, so in this case, it is 200 AAL.
- **Aircraft category** is based on approach speed (Vref × 1.3): Cat A < 91 kt, Cat B 91–120 kt, Cat C 121–140 kt, Cat D 141–165 kt. Most airliners are Cat C or D.

### The Profile View

The profile view is read left to right (inbound). Key items:

- **Glideslope/path angle** — for an ILS, typically 3.00°. Non-standard glideslopes (e.g. 3.5°) are clearly marked.
- **FAF (Final Approach Fix)** — the point where you are established on the final approach course at the correct altitude to begin descent. Shown as a Maltese cross (✖) on the profile.
- **Step-down fixes** — on non-precision approaches, intermediate fixes where you can descend to progressively lower altitudes after crossing them.
- **DA or MDA** — shown as a dashed horizontal line near the runway end.
- **Missed approach** — the profile shows the initial climb of the missed approach procedure, including the climb gradient required.

---

## 4. Airport/Ground Charts

Airport charts show the surface layout including runways, taxiways, aprons, terminals, and hotspots.

### Key Elements

**Runways** — thick dark bars labelled with their magnetic heading in tens of degrees (e.g. runway 03L, 03R, 21R, 21L).

**Taxiways** — labelled with letters (Alpha, Bravo, etc.) or letter-number combinations (B1, B2). These match the phonetic names used by ground/tower ATC.

**Holding positions** — dashed yellow lines across taxiways. Do not cross these without ATC clearance. On a chart these are shown as a thick line perpendicular to the taxiway.

**Hot spots** — numbered circles (HS 1, HS 2) marking areas of known collision or incursion risk. The chart legend explains each one.

**Apron/gate areas** — typically shaded. Gate numbering matches the aerodrome's real layout.

**Frequencies** — ground and tower frequencies are often printed in the chart header for quick reference.

### Reading a Taxi Clearance Against the Chart

When ground issues `"Taxi to holding point B runway 03L via Delta and Alpha"`, trace the path on the chart: from your gate, find taxiway D (Delta), follow it to A (Alpha) toward the holding point B runway 03L.

---

## 5. En-Route Charts

En-route charts (also called airway charts) cover the cruise phase of flight. They come in two types: **Low Altitude** (below FL180 in the US, generally below FL245 in ICAO regions) and **High Altitude** (above those levels).

### Key Elements

**Airways** — named routes connecting VORs, NDBs, or waypoints. Low-altitude airways are prefixed `V` (VOR airways, US) or `L` (ICAO). High-altitude airways use `J` (US) or `UN`, `UL` (ICAO).

**MEA (Minimum En-Route Altitude)** — the lowest altitude ensuring obstacle clearance and navigation signal reception along an airway segment. Printed above the airway line.

**MOCA (Minimum Obstacle Clearance Altitude)** — provides obstacle clearance but only guarantees nav signal within 22 NM of a VOR. Shown with an asterisk (*).

**Distance** — mileage between fixes is printed along the airway.

**Compulsory vs non-compulsory reporting points** — solid triangles (▲) are compulsory position reports; open triangles (△) are non-compulsory.

**ADIZ / FIR boundaries** — shown as thick dashed lines, denoting airspace boundaries.

---

## Common Symbols & Conventions

| Symbol | Meaning |
|---|---|
| ✖ (Maltese cross) | Final Approach Fix (FAF) |
| ⊕ | Waypoint / named fix |
| ◆ | Compulsory reporting point |
| ◇ | Non-compulsory reporting point |
| ▽ (downward triangle) | DME fix |
| Circle with arrows | Holding pattern |
| Dashed oval | Terminal holding fix |
| MSA circle | Minimum Safe Altitude by sector (usually 25 NM radius) |
| D- prefix | DME arc (e.g. D16 = 16 DME arc) |
| T- prefix | TACAN |
| `C` in a circle | Circle-to-land procedure available |
| Bold X | Missed approach point (non-precision) |

### Altitude Notation

| Notation | Meaning |
|---|---|
| `12000` | 12,000 ft MSL |
| `FL120` | Flight Level 120 (12,000 ft, using standard pressure 1013.25 hPa) |
| `+12000` or `12000A` | At or above 12,000 ft |
| `-8000` or `8000B` | At or below 8,000 ft |
| `8000A / FL130B` | Between 8,000 and FL130 |

### Speed Notation

Speeds on charts are always **indicated airspeed (KIAS)** unless annotated otherwise. `210KT` means 210 knots indicated.

---

## Reading a Chart Step-by-Step

### Before Departure

1. Pull the SID for your departure runway and read the full procedure name and applicable runways.
2. Check the climb gradient — can your aircraft meet it?
3. Note the initial heading/course and first altitude restriction.
4. Identify which transition ATC has assigned (or request clarification on departure).
5. Brief the missed approach on the approach chart for your destination.

### On Arrival

1. Load the STAR and identify your entry transition fix.
2. Note all altitude constraints — programme them into your FMS.
3. Confirm the speed restrictions and plan your deceleration profile.
4. Identify the IAF where the STAR ends and the approach begins.
5. Brief the approach:
   - Course and glideslope/path angle
   - FAF altitude
   - DA or MDA
   - Missed approach procedure (first heading, altitude, then routing)
   - Required visibility

### During the Approach

- At the FAF, call out the altitude and confirm you are established on the approach course.
- Cross-check your altitude against the profile view at step-down fixes or during glideslope descent.
- At DA/MDA, have the required visual references or fly the missed approach — no exceptions.

---

## Chart Providers

| Provider | Coverage | Free? | Notes |
|---|---|---|---|
| [Navigraph](https://navigraph.com) | Worldwide (Jeppesen-based) | Subscription | Most popular on VATSIM; integrates with MSFS, X-Plane, P3D |
| [Chartfox](https://chartfox.org) | Worldwide (official AIP charts) | Free (VATSIM login) | Uses government-published charts; free for VATSIM members |
| [SkyVector](https://skyvector.com) | FAA charts (US/Canada primary) | Free | Great for en-route planning; includes IFR low/high charts |
| [AIP (national providers)](https://www.icao.int/safety/airnavigation/AIG/Pages/AIP.aspx) | Country-specific | Often free | Each country publishes its own AIP; quality varies |

> **VATSIM tip:** Chartfox is the recommended free option for VATSIM members. It pulls directly from official government AIPs and is accessible at [chartfox.org](https://chartfox.org) after logging in with your VATSIM account.

---

## Quick Reference: Approach Minimums Decoded

```
ILS RWY 03L
────────────────────────────────────────────────────────
CATEGORY            A         B         C         D
DA(H)            287(200)  287(200)  287(200)  287(200)
VIS               R550M     R550M     R550M     R550M
────────────────────────────────────────────────────────
CIRCLING
MDA(H)           460(373)  500(413)  560(473)  660(573)
VIS (M)           V1500M    V1600M    V2400M    V3600M
────────────────────────────────────────────────────────
```

- **DA 287** means descend to 287 ft MSL, then decide: land or go missed.
- **(200)** is the height above the runway threshold elevation (HAT), useful for a quick sanity check.
- **VIS R550M** means you need 550M of runway visual range reported by the airport sensors.
- **Circling MDA** applies if you need to circle to land on a different runway than the one the approach is designed for.
- **VIS V1500M** means you need 1500M of horizontal visibility to perform the approach. Notice how it increases with Aircraft category.

---

*For VATSIM use, always cross-check your charts with current NOTAMs and confirm procedures with ATC. Chart effective dates matter — always use the current AIRAC cycle (updated every 28 days).*

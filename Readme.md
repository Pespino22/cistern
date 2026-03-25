# DIY Cistern Thermal Battery - Rough Draft Build Outline

> **Concept:** Two insulated 3,000-gallon cisterns sit side by side indoors. Cistern 1 collects cold rainwater from the roof and serves as the cold reserve. Cistern 2 is the thermal battery copper immersion(or outside wrapping coils) coils let the HVAC system dump heat into the water, and that warm water is sent to the plants for irrigation. As warm water leaves Cistern 2, cold water flows in from Cistern 1 to recharge the battery. The battery always has cold water ready to steal heat from.

---

## The Big Idea at a Glance

- **Storage capacity (Cistern 2):** ~500,400 BTU (~146.7 kWh)
- **Temperature swing:** 52°F (fully charged) → 72°F (fully discharged / at room temp)
- **Cooling runway:** ~49.8 hours from full charge (52°F); ~39.8 hours remaining if water is at 60°F
- **Recharge method:** Warm water out to plants, cold water in from Cistern 1 - no electricity for refrigeration
- **Estimated cost:** ~$6,542 total implementation / ~$1,704–$3,640 DIY
- **Projected payback:** ~8.5 months on total implementation cost, with ~$8,807/year combined savings (energy + water)

---

## System Architecture - Two Cisterns Side by Side, Indoors

```
[Roof Catchment]
     ↓ gutters + downspouts + first-flush diverter
     ↓
┌─────────────────────────┐       ┌─────────────────────────────────┐
│   CISTERN 1             │       │   CISTERN 2                     │
│   Cold Reserve          │       │   Thermal Battery               │
│   (Insulated)           │ ───── │   (Insulated)                   │
│                         │ float │                                 │
│   Collects rainwater    │ valve │  ┌──┐ ┌──┐ ┌──┐  3 copper     │
│   Stores at ~52°F       │ ───►  │  │()│ │()│ │()│  immersion    │
│   Feeds Cistern 2       │       │  │()│ │()│ │()│  coils        │
│                         │       │  └──┘ └──┘ └──┘               │
│                         │       │      ↑         ↓               │
└─────────────────────────┘       │   [HVAC Loop — 75°F in,        │
                                  │    cooled fluid out]            │
                                  │                                 │
                                  │   Warm water (68–72°F) ──────►  IRRIGATION
                                  │   out to plants                 │
                                  └─────────────────────────────────┘
```

**Cistern 1 - The Cold Reserve (Insulated, Indoors)**
- 3,000-gallon insulated tank
- Fed by roof rainwater collection
- Stores water at ~52°F (insulation keeps it cold indoors)
- Float-valve feeds cold water into Cistern 2 as the battery level drops

**Cistern 2 - The Thermal Battery (Insulated, Indoors)**
- 3,000-gallon insulated tank containing 3 copper immersion coils
- HVAC loop dumps heat into the water via the coils
- Warm water (68–72°F) drains to irrigation / vertical farm nutrient tanks
- Float valve auto-refills from Cistern 1 with cold water

### Why Both Indoors and Insulated?
- **Cistern 1 insulation** keeps the cold reserve from warming up to room temperature while it waits to recharge the battery
- **Cistern 2 insulation** ensures the *only* heat entering the battery is from the HVAC coils - no ambient heat gain through the tank walls stealing your cooling capacity
- **Side by side** minimizes the pipe run between tanks and allows gravity feed if plumbed at the same level
- **Indoor placement** provides year-round freeze protection (critical for Chicago winters) and easy access for maintenance

---

## Phase 1 - Cistern Setup (Both Tanks)

### Cistern 1 - The Cold Reserve
- **Size:** 3,000 gallons
- **Location:** Indoors, adjacent to Cistern 2
- **Type:** Polyethylene vertical tank or manifolded IBC totes
- **Insulation:** Wrap with rigid foam board (2" minimum) or spray foam to keep water at ~52°F in a room-temperature environment
- **Inlet:** Roof rainwater collection (gutters → downspouts → first-flush diverter → screen filter → Cistern 1)
- **Outlet:** Float-valve-controlled feed line to Cistern 2
- **Overflow:** Standard overflow outlet routed to exterior drain (for heavy rain events)

### Cistern 2 — The Thermal Battery
- **Size:** 3,000 gallons 
- **Location:** Indoors, adjacent to Cistern 1 and near HVAC system
- **Type:** Polyethylene vertical tank or manifolded IBC totes
- **Insulation:** Same as Cistern 1 - wrap with rigid foam board or spray foam
- **Access:** Top hatch large enough to lower in 3 copper coils
- **Inlet:** Float-valve feed from Cistern 1 (cold water in)
- **Outlet:** Flush valve to irrigation line (warm water out to plants)

### Critical Structural Note
Both tanks together hold 6,000 gallons This requires:
- A reinforced concrete slab rated for the weight of 6,000 gallons (with safety margin)
- Engineering review of the floor/foundation before installation

### Key Decisions
- **Single tanks vs. IBC totes?** A single 3,000-gal poly tank per cistern is simplest. Alternatively, ganging ~eleven 275-gal IBC totes (6 for one cistern, 5 for the other) is cheaper but requires manifold plumbing
- **Insulation type:** Rigid foam board (XPS/EPS, R-5 per inch) is cheapest DIY; spray foam gives better coverage on curved tank surfaces
- **Transfer between tanks:** At the same floor level, a short horizontal pipe with a float valve in Cistern 2 works. If tanks are offset vertically, gravity or a small transfer pump

---

## Phase 2 — Heat Exchanger (Immersion Coils)

Three copper coils sit inside Cistern 2 (the thermal battery) so your HVAC loop can dump heat into the water.

### Bill of Materials (Heat Exchanger) — With 20% Cost Buffer
| Item | Spec | Base Cost | +2 |
|---|---|---|---|
| Copper immersion coils | 3× 32 ft coils, ½" diameter | $449.97 ($150 ea) | **~$540 ($180 ea)** |
| Circulation pump | 1/8 HP | ~$50–100 | **~$60–120** |
| Fittings, connectors, unions | Copper/brass to connect coils to HVAC loop | ~$50–100 | **~$60–120** |
| **Subtotal** | | **$645** | **~$774** |

### Build Notes
- **Coil surface area:** π × 0.0417 ft × 32 ft = ~4.19 sq ft per coil × 3 = **12.57 sq ft total**
- **Heat transfer coefficient (U):** ~40 BTU/hr·ft²·°F (middle-ground estimate for copper-in-water)
- **Heat transfer at full charge (52°F water, 75°F HVAC loop):** ~10,053 BTU/hr*
- **Heat transfer at 60°F water (75°F HVAC loop):** ~7,540 BTU/hr
- **Rated manifold capacity:** approx 10,000–15,000 BTU/hr
- **Installation:** Internal drop-in — lower coils through Cistern 2's top access hatch, route inlet/outlet pipes up and out to the HVAC loop

> *Math note: Using Q = U × A × ΔT with HVAC loop at 75°F and water at 52°F gives ΔT = 23°F and Q = 11,561 BTU/hr. The spreadsheet's 10,053 figure uses ΔT = 20°F (the storage swing from 52→72°F). The 7,540 BTU/hr at 60°F water correctly uses 75 − 60 = 15°F. The discrepancy at 52°F doesn't affect the core design — 10,053 is more conservative, which is appropriate for planning purposes.

### Coil Fabrication Tips
1. Buy ½" soft copper tubing in 50 ft rolls (trim to 32 ft per coil)
2. Wrap tightly around a 5-gallon bucket or similar form to create a helical coil
3. Leave straight tails at each end (12–18") for routing out of the tank
4. Use compression fittings or solder unions at the tank penetration points
5. Pressure-test each coil with air before dropping it in — any leak underwater is a pain to fix

---

## Phase 3 - Plumbing the Flows

### Flow 1: Roof → Cistern 1 (Rainwater Collection)
```
[Roof catchment]
     ↓ gutters + downspouts
[First-flush diverter + screen filter]
     ↓
[Cistern 1 — Cold Reserve (insulated, indoors)]
```

### Flow 2: Cistern 1 → Cistern 2 (Cold Recharge)
```
[Cistern 1 — Cold Reserve (~52°F)]
     ↓ float valve in Cistern 2 opens as level drops
[Cistern 2 — Thermal Battery] ← cold water recharges battery
```


### Flow 3: HVAC Heat Absorption Loop (Closed)
```
[HVAC / Heat Source]
     ↓ warm fluid (75°F)
[Circulation Pump (1/8 HP)]
     ↓
[3× Copper Coils in Cistern 2] ← heat transfers into water
     ↓ cooled fluid
[Return to HVAC]
```
- Closed loop - same fluid circulates (water or water/glycol mix)
- 1/8 HP pump is sufficient for the low flow resistance of ½" coils
- The only heat source entering Cistern 2 should be through these coils (insulation prevents ambient heat gain)

### Flow 4: Cistern 2 → Irrigation (Warm Water to Plants)
```
[Cistern 2 (water at 68–72°F)]
     ↓ flush valve opens when temp > 70°F
[Irrigation line / Nutrient Tanks / Vertical Farm]
```

### Why This Dual-Cistern Cycle Works
- **Battery always has cold water:** Cistern 1 is a dedicated cold reserve, so Cistern 2 is never starved for recharge
- **Overflow prevention:** irrigation empties Cistern 2  making room for cold input from Cistern 1
- **Free recharge:** Cold-swap from Cistern 1 resets the thermal battery with zero electricity for refrigeration
- **Plant benefit:** Water leaves the battery at ~68–70°F, the ideal temperature for nutrient uptake in most crops — no cold shock, no heating cost
- **Both tanks insulated:** Cistern 1 stays cold (ready to recharge), Cistern 2 only gains heat through the coils (maximizing controllable cooling)

---

## Phase 4 — Automation & Sensors

### Sensor Layout — Both Cisterns

| Location | Sensor | Purpose | Trigger |
|---|---|---|---|
| **Cistern 1** | Water level sensor | Track cold reserve supply | Low-level alert → conserve water / check roof collection |
| **Cistern 1** | Temperature probe | Verify reserve is staying cold | Alert if water warms above 58°F (check insulation) |
| **Cistern 2** | Water temperature probe | Track battery charge state | Temp > 70°F → open flush valve to irrigation |
| **Cistern 2** | Float valve (mechanical) | Auto-refill from Cistern 1 | Level drops → cold water flows in |
| **Cistern 2** | Water level sensor (optional) | Dashboard / safety | Low-level alarm if Cistern 1 is depleted |
| **Coil loop** | Flow meter (optional) | Monitor heat exchange rate | Data logging |

### "Battery Status" Dashboard
- **Cistern 2 temp:** 52°F = fully charged → 72°F = fully discharged
- **At 60°F:** ~300,240 BTU remaining (~39.8 hours of cooling)
- **Cistern 1 level:** How much cold recharge water is available
- **Cistern 1 temp:** Confirms reserve is staying cold (~52°F target; alert if above 58°F — insulation may be failing)

### Arduino Trigger Logic (Simplified)
```
// CISTERN 2 - Thermal Battery
IF cistern2_temp > 70°F:
    OPEN flush valve → drain warm water to irrigation
    // Float valve auto-refills with cold water from Cistern 1

IF cistern2_temp < 55°F:
    CLOSE flush valve → battery is charged, conserve water

// CISTERN 1 — Cold Reserve  
IF cistern1_level < 20%:
    ALERT → "Cold reserve low — reduce irrigation or check roof collection"
    // Optionally: close Cistern 2 flush valve to preserve remaining battery charge

IF cistern1_temp > 58°F:
    ALERT → "Reserve water warming — check insulation on Cistern 1"
```


## Projected Performance & Economics

### Thermal Performance (from Cistern 2)
| Metric | Value | How It's Calculated |
|---|---|---|
| Water mass (Cistern 2) | 25,020 lbs | 3,000 gal × 8.34 lbs/gal |
| Temperature range | 52°F → 72°F (ΔT = 20°F) | Initial charge → room temp |
| Total energy stored | 500,400 BTU | 25,020 lbs × 20°F × 1 BTU/lb·°F |
| Electrical equivalent | ~146.7 kWh | 500,400 ÷ 3,412 BTU/kWh |
| Heat transfer at full charge | ~10,053 BTU/hr | U × A × ΔT (see math note) |
| Heat transfer at 60°F water | ~7,540 BTU/hr | 40 × 12.57 × (75−60) |
| Time to full charge (52→72°F) | ~49.8 hours | 500,400 ÷ 10,053 |
| Remaining capacity at 60°F | 300,240 BTU / 39.8 hrs | 25,020 × 12°F / 7,540 BTU/hr |

### Daily & Annual Savings
| Metric | Value | How It's Calculated |
|---|---|---|
| Daily operating hours (est.) | ~12 hours | Peak cooling period |
| Daily heat absorbed | ~120,637 BTU | 10,053 BTU/hr × 12 hrs |
| Daily energy offset | ~35.36 kWh | 120,637 ÷ 3,412 |
| Implied electricity rate | ~$0.14/kWh | Chicago residential rate |
| Daily energy savings | ~$4.95 | 35.36 kWh × $0.14 |
| Annual energy savings | ~$1,807 | $4.95 × 365 |
| Electrical power offset | ~2.21 kW | 35.36 kWh ÷ ~16 hrs |
| Daily carbon offset | ~23.87 lbs CO2 | Uses IL grid factor (~0.675 lbs/kWh) |
| Annual rainwater harvested | ~1,227,000 gal | Based on roof catchment area |
| Chicago water utility rate | $4.89 / 1,000 gal | Municipal rate |
| Annual water savings | ~$6,000 | 1,227,000 × $4.89/1,000 |
| **Total annual return** | **~$7,807** | $1,807 + $6,000 |

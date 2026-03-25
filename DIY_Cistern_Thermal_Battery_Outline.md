# DIY Cistern Thermal Battery — Rough Draft Build Outline

> **Concept:** A 3,000-gallon rainwater cistern that doubles as a passive cooling battery. Cold rainwater absorbs heat from your space via copper immersion coils, then the warmed water is flushed to irrigation and replaced with fresh cold rain — recharging the battery for free.

---

## The Big Idea at a Glance

- **Storage capacity:** ~500,400 BTU (~147 kWh) — roughly equivalent to 11 Tesla Powerwalls of thermal energy
- **Temperature swing:** 52°F (fresh rainwater) → 72°F (fully "discharged")
- **Cooling runway:** ~39–49 hours of continuous heat absorption before the water reaches room temp
- **Recharge method:** Flush warm water to plants, refill with cold rainwater — no electricity needed
- **Estimated DIY cost:** $1,420–$2,200 (roughly $100–$150 per kWh of capacity)
- **Projected payback:** ~7 months, with ~$7,800/year combined savings (energy + water)

---

## Phase 1 — Cistern Setup

### What You Need
- A 3,000-gallon water tank (polyethylene, IBC totes ganged together, or a buried cistern)
- Roof rainwater collection system (gutters, downspouts, first-flush diverter, basic filtration)
- Float valve to auto-refill from your rainwater supply when the tank level drops

### Key Decisions
- **Above-ground vs. buried?** Buried stays cooler naturally (ground temp ~52–55°F in Chicago), but above-ground is easier for DIY access and coil installation
- **Single tank vs. multiple IBC totes?** A single 3,000-gal poly tank is simplest; ganging six 275-gal IBC totes is cheaper but requires manifolding
- **Location:** As close to the HVAC system and irrigation zone as practical to minimize pipe runs

---

## Phase 2 — Heat Exchanger (Immersion Coils)

This is the heart of the system. You're dropping copper coils into the cistern so your HVAC loop can dump heat into the water.

### Bill of Materials (Heat Exchanger)
| Item | Spec | Est. Cost |
|---|---|---|
| Copper immersion coils | 3× 32 ft coils, ½" diameter | ~$450 ($150 each) |
| Circulation pump | 1/8 HP | ~$50–100 |
| Fittings, connectors, unions | Copper/brass to connect coils to HVAC loop | ~$50–100 |
| **Subtotal** | | **~$645** |

### Build Notes
- **Coil type:** Pre-formed ½" copper coil (sold at plumbing suppliers in 20–50 ft rolls). You can coil it yourself around a bucket or barrel to form the helix shape
- **Total coil surface area:** ~12.6 sq ft across all 3 coils — this is what drives your heat transfer rate
- **Heat transfer coefficient (U):** ~40 BTU/hr·ft²·°F (a reasonable middle-ground estimate for copper-in-water)
- **Resulting heat transfer rate:** ~7,500–10,000 BTU/hr depending on water temp and flow
- **Installation:** Internal drop-in — just lower the coils into the tank through the top access hatch, with inlet/outlet pipes running up and out to your HVAC loop

### Coil Fabrication Tips
1. Buy ½" soft copper tubing in 50 ft rolls (you'll trim to 32 ft per coil)
2. Wrap tightly around a 5-gallon bucket or similar form to create a helical coil
3. Leave straight tails at each end (12–18") for routing out of the tank
4. Use compression fittings or solder unions at the tank penetration points
5. Pressure-test each coil with air before dropping in — any leak underwater is a pain to fix

---

## Phase 3 — Plumbing the Loop

### Charging Cycle (Absorbing Heat)
```
[HVAC / Heat Source] 
     ↓ warm fluid (75°F)
[Circulation Pump (1/8 HP)]
     ↓
[Copper Coils in Cistern] ← heat dumps into water
     ↓ cooled fluid
[Back to HVAC / Heat Source]
```

### Discharge Cycle (Flushing & Recharging)
```
[Cistern warm water (68–72°F)]
     ↓ gravity or pump
[Irrigation / Nutrient Tanks] ← plants love lukewarm water
     ↓ tank level drops
[Float Valve triggers]
     ↓
[Fresh cold rainwater (52°F) fills cistern] ← battery recharged
```

### Why the Dual Cycle Is Genius
- **Overflow prevention:** Using ~5,500 gal/day for irrigation empties the tank nearly twice daily, always making room for new rain
- **Free recharge:** Replacing warm water with cold rain resets the thermal battery with zero electricity
- **Plant benefit:** Cold 52°F rainwater can shock roots — but after serving as a heat sink, it warms to ~68–70°F, which is the ideal range for nutrient uptake

---

## Phase 4 — Automation & Sensors

The system needs basic automation to know when to flush and refill. An Arduino or similar microcontroller can handle this.

### Sensor Logic
| Sensor | Purpose | Trigger |
|---|---|---|
| Water temperature probe (in tank) | Track battery charge state | If temp > 70°F → open flush valve |
| Float valve / water level sensor | Maintain tank level | If level drops → open rainwater inlet |
| Optional: flow meter on coil loop | Monitor heat exchange rate | Data logging |

### "Battery Status" Dashboard (Optional)
- **Initial water temp:** 52°F (fully charged)
- **Max functional temp:** 72°F (fully discharged — water = room temp, no more cooling)
- **Current temp → remaining capacity:** e.g., at 60°F, you still have ~300,000 BTU (~30+ hours) of sink capacity left

### Arduino Trigger Logic (Simplified)
```
IF tank_temp > 70°F:
    OPEN flush valve (drain warm water to irrigation)
    // Float valve auto-refills with cold rainwater
    
IF tank_temp < 55°F:
    CLOSE flush valve (battery is charged, conserve water)
```

---

## Phase 5 — Tying It All Together

### Full System Checklist
- [ ] Cistern installed and plumbed to rainwater collection
- [ ] 3 copper immersion coils fabricated and dropped into tank
- [ ] Coil loop connected to HVAC system with circulation pump
- [ ] Drain/flush line plumbed to irrigation or nutrient tanks
- [ ] Float valve installed to auto-refill from rainwater reservoir
- [ ] Temperature sensor installed in tank
- [ ] Arduino/controller wired to flush valve and temp sensor
- [ ] System tested: run HVAC loop, watch water temp rise, confirm flush/refill cycle works

---

## Projected Performance & Economics

| Metric | Value |
|---|---|
| Heat transfer rate (3 coils) | ~10,000 BTU/hr |
| Time to full charge (52→72°F) | ~49 hours |
| Daily energy offset | ~35 kWh/night |
| Annual energy savings | ~$1,807 |
| Annual rainwater harvested | ~1.2M gallons |
| Annual water utility savings | ~$6,000 |
| **Total annual return** | **~$7,807** |
| Total DIY implementation cost | ~$1,420–$2,200 |
| **Simple payback period** | **~7 months** |
| Return on investment | ~169% |

---

## Safety & Practical Notes

- **Water treatment:** If the cistern also serves irrigation, consider a basic screen/filter on the inlet to keep debris out of the coils
- **Legionella risk:** This system stays below 72°F and is non-potable — Legionella is primarily a concern in hot water systems (above 77°F), but keep the system moving and don't let water stagnate
- **Permits:** Check local codes for rainwater harvesting and any cistern size restrictions in your area. Chicago allows rainwater harvesting — verify current rules for your specific setup
- **Insulation:** If the tank is above-ground, insulating it helps prevent ambient heat gain on hot days
- **Winter:** In freezing climates, the system is seasonal for cooling. Drain coils or use antifreeze in the HVAC loop if temps drop below 32°F, or switch to a heating-assist mode if the cistern is buried (ground stays ~52°F year-round)

---

## What This Draft Doesn't Cover Yet

- Detailed plumbing diagrams and pipe sizing
- Specific Arduino wiring schematics and code
- Rainwater collection sizing (roof area → gallons)
- Integration with specific HVAC systems (mini-splits, forced air, hydronic)
- Structural considerations for a 25,000 lb water mass
- Permitting and inspection requirements by jurisdiction

---

*This is a rough draft outline based on the design spreadsheet. All numbers are estimates — real-world performance will vary with climate, insulation, coil craftsmanship, and usage patterns.*

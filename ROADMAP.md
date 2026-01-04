<!-- Copyright (c) Manfred Foissner. All rights reserved. See LICENSE.txt. -->

# 🚀 BONZOOKAA v2 — Exploration Mode Roadmap (Master)

**Leitbild:** *Endlos-Exploration mit Depth (Tiefe) als Master-Achse (Hybrid „C“) + weighted Mod-Unlocks („B“).*  
**Konsequenz:** Jede Zone ist seed-basiert prozedural, kein Run gleicht dem nächsten. Tiefe steuert Eskalation.

---

## 0) Release-Management

### Master-Artefakt
- **`BONZOOKAA_v2_FULL_CONSISTENT_*.zip`** ist der **einzige** deploybare Stand.
- Alle Einzelpatches gelten als **deprecated**, sobald ein neuer Full-ZIP existiert.

### Projektdateien-Limit (25 Dateien, keine Ordner)
Empfohlenes Set in den Projektdateien:
1. `MASTER_BUILD.zip` *(jeweils der aktuelle Full-Stand; umbenennen beim Upload)*  
2. `ROADMAP.md` *(dieses Dokument)*  
3. `CHANGELOG.md` *(laufende Änderungen)*  
4. optional: `KNOWN_ISSUES.md` *(nur wenn nötig)*

Damit bleibt ihr stets reproduzierbar, auch wenn Repo/Cache/Device „komisch“ spielt.

---

## 1) Status — Core Architecture (DONE)

| System | File | Status |
|---|---|---|
| Seeded Random | `runtime/world/SeededRandom.js` | ✅ |
| Camera System | `runtime/world/Camera.js` | ✅ |
| Map Generator | `runtime/world/MapGenerator.js` | ✅ *(Range-Robustness + Caps)* |
| World Manager | `runtime/world/World.js` | ✅ *(Zone bounds, boss bounds)* |
| Scene Manager | `runtime/world/SceneManager.js` | ✅ |
| Acts Config | `data/acts.json` | ✅ |
| Hub Modal | `index.html` | ✅ |
| Game Loop | `main.js` | ✅ |
| Enemy Level Scaling | `runtime/Enemies.js` | ✅ *(Δ≈1.5 + Depth/Tier hooks)* |
| Map Editor Tool | `tools/mapEditor.html` | ✅ |
| Collision Core | `runtime/Collision.js` | ✅ *(soft slide, bullet vs obstacle, mines)* |
| Damage Telemetry | `runtime/DamageTelemetry.js` | ✅ |
| Hit Flash/Vignette | `runtime/HitFlash.js` | ✅ |

---

## 2) Depth System (Master Progression)

### 2.1 Depth = Master-Achse (Hybrid C)
- Jede Zone erhöht **Depth +1**
- **Milestones** (z. B. alle 25 Depth) erhöhen Systemkomplexität
- Tiefe steuert:
  - Enemy density
  - Elite chance
  - Environment modifier slots
  - Loot complexity (später)

### 2.2 Weighted Unlocks (B)
- Pro Milestone wird **ein Modifier** aus einem Pool per Gewichtung freigeschaltet
- Pro Zone werden aktive Mods **random** aus dem freigeschalteten Pool gezogen

**Goal:** endlos, aber nicht planlos — die „Regeln“ wachsen mit der Tiefe.

---

## 3) Phase 2 — Polish & Testing (NEXT)

### 3.1 World-Coord Consistency (HIGH)
- [ ] Enemy targeting vollständig auf **World-Coords** (Camera screen→world) umstellen  
- [ ] Pickup attraction korrekt in World-Coords (keine Linien-Artefakte)  
- [ ] Boss/Elite spawn points ausschließlich in Zone-Bounds

### 3.2 Enemy AI Improvements (HIGH)
`runtime/AI.js` *(NEW)*  
- [ ] Aggro radius detection (world-space)
- [ ] Chase + return-to-patrol
- [ ] Line-of-sight (Collision)
- [ ] Basic group coordination

### 3.3 Portal System Enhancement (MED)
- [ ] Portal animation + enter transition
- [ ] Return portal in hub
- [ ] Hub feedback (Depth reached, mods unlocked)

---

## 4) Phase 3 — Hub Features (MED)

### 4.1 Vendor System
- [ ] buy/sell scrap
- [ ] refresh on milestone / act completion
- [ ] buyback

### 4.2 Skill Station
- [ ] skill tree visualization
- [ ] respec (scrap cost)
- [ ] preview

---

## 5) Phase 4 — Content (MED)

### 5.1 More Acts (Themes)
- [ ] Derelict Fleet
- [ ] Black Hole Approach
- [ ] Enemy Mothership

### 5.2 Enemy Archetypes (Diablo-DNA)
- [ ] Bruiser / Sniper / Support / Exploder / Summoner / Turret
- [ ] Elite affixes (small set, high impact)

---

## 6) Phase 5 — Performance (LOW → später)

- [ ] `runtime/SpatialHash.js`  
- [ ] object pooling (bullets/enemies/pickups/particles)  
- [ ] offscreen canvas for static layers

---

## 7) Known Risks / Guardrails

- **Procedural generation must be total**: no infinite loops → keep spawn caps + fallback zones.
- **Readability is king**: Background vs Obstacle vs Hazard muss klar getrennt sein.
- **One master build**: keine Patch-Ketten im Repo deployen.

---

*Last updated: 2026-01-04*

<!-- Copyright (c) Manfred Foissner. All rights reserved. See LICENSE.txt. -->

# CHANGELOG — BONZOOKAA v2 (Master)

Format orientiert an *Keep a Changelog* (pragmatisch), Versionsschema: `v2.YYYY.MM.DD`.

---

## v2.2026.01.04

### Added
- World-space Exploration Core (SeededRandom, Camera, World/Scene Manager)
- Collision System (soft slide), bullet vs obstacle, mines (contact + bullet hit)
- Damage Telemetry (direction + label + numbers)
- Hit Flash/Vignette per damage type
- Procedural generation guards (spawn caps + fallbacks)

### Changed
- Map generation supports range configs (`width/height` arrays)
- World bounds used instead of canvas bounds (prevents boss/enemy “strafe off”)
- Stabilized load/start flow on mobile (guards)

### Fixed
- Player spawn at (0,0) when range-config treated as scalar
- Various “UI only / black screen” states caused by invalid zone init (guards)

### Notes
- Deploy ausschließlich über **Full-ZIP Master** (kein Patch-Stack).
- Bei mobilen Tests: Hard refresh / cache kill nach Deploy.

---

## How to add entries
Nach jeder größeren Änderung:
1. Datumsversion anlegen
2. `Added/Changed/Fixed` füllen
3. 1–2 Sätze “Reason/Impact”

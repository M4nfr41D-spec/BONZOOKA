<!-- Copyright (c) Manfred Foissner. All rights reserved. See LICENSE.txt. -->

# MASTER UPLOAD — Projektdateien (25 Dateien Limit)

## Ziel
Reproduzierbarer Stand trotz Upload-Limit.

## Upload Set (empfohlen)
1. `MASTER_BUILD.zip`  ← aktueller Full-Stand (z. B. BONZOOKAA_v2_FULL_CONSISTENT_*.zip umbenennen)
2. `ROADMAP.md`
3. `CHANGELOG.md`
4. optional: `KNOWN_ISSUES.md`

## Deployment-Regeln
- Keine Einzelpatches im Repo mischen.
- Bei neuen Fixes immer zuerst lokal testen, dann **neuen Full-ZIP** erzeugen.
- Nach Deploy: Hard refresh (iOS: Tab schließen, neu öffnen).

## Minimal Debug-Workflow (ohne Devtools)
- Wenn nur UI sichtbar: vermutlich Zone/World init fehlgeschlagen → Full-ZIP erneut deployen + cache kill.

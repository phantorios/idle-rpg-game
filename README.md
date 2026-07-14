# Idle RPG Prototype

A playable idle/clicker RPG prototype — tap combat, exponential upgrade economies, and stage/boss progression — built as a single dependency-free HTML file.

**▶ [Play it live](https://YOUR_USERNAME.github.io/idle-rpg/)**

## What it is

A rapid prototype for validating the core loop of an idle RPG (farm → level up → upgrade → repeat) before committing balance numbers to engine code. Inspired by Tap Titans and RO Clicker.

Features:

- Tap combat with crits, floating damage numbers, and squash-and-stretch feedback
- Two idle heroes providing auto-DPS (the "idle" in idle RPG)
- Stage progression: 10 kills summon a timed boss; fail and you fall back to farming
- Big-number formatting (K / M / B / T / aa…) for the genre's exploding economies
- **Live balance tuner** (⚙ button): adjust HP growth, gold growth, upgrade cost growth, boss multiplier, and boss timer at runtime and feel the difficulty curve change

## Design notes

All balance constants live in a single `DEFAULTS` object at the top of the script — the contract that would be ported to a game engine as a config resource. The key relationship: **gold growth must stay below HP growth**; the gap between the two is the difficulty curve.

Defaults follow genre conventions: ~1.55× monster HP per stage, 1.15× upgrade cost per level.

## Run locally

No build step, no dependencies:

```
open index.html
```

## Roadmap

- Port the validated loop to Godot 4 for Android
- Prestige / rebirth meta layer
- Team management and equipment upgrades

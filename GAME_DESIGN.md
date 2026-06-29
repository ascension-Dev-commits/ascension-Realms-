# Game Design Document — Ascension Realms: Pet System

## Core Vision
Ascension Realms is a browser-based open-world RPG where the player chooses a companion pet and battles through escalating encounters. The game prioritizes **feel** — snappy animations, satisfying feedback, and a sci-fi aesthetic.

## Pet Design Philosophy

Each pet should feel distinct — not just stat differences but a different playstyle.

### Stat Ranges (Base Level)
| Stat | Min | Max | Notes |
|---|---|---|---|
| HP | 80 | 140 | Higher HP = tankier |
| ATK | 15 | 35 | Damage per hit |
| DEF | 10 | 30 | Damage reduction |
| SPD | 10 | 30 | Turn order priority |

### Type Effectiveness
```
Fire      → strong vs Nature,   weak vs Water
Water     → strong vs Fire,     weak vs Electric
Electric  → strong vs Water,    weak vs Nature
Nature    → strong vs Electric, weak vs Fire
Dark      → neutral, ignores 15% DEF
Light     → neutral, bonus vs Dark
```

## Battle System

### Damage Formula
```
damage = ATK × type_multiplier − (DEF × 0.5)
minimum damage = 1
critical chance = 10%, multiplier = 1.5×
```

### Special Abilities
Each pet has one ability with a 3-turn cooldown.

## Visual Style Guide

- **Palette:** Void `#05060A`, Cyan `#00E5FF`, Red `#FF3B30`, Amber `#FFB020`
- **Fonts:** Orbitron (display), Rajdhani (UI), JetBrains Mono (numbers)
- **Effects:** Scanlines, vignette, corner brackets

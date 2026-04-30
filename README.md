# FlowGrid

A mobile-first puzzle game where you connect colored dots on a grid by drawing paths — with a catch: every single cell on the board must be covered. No gaps allowed.

## How to play

1. Press on any colored dot and drag to start drawing a path.
2. Connect it to the matching dot of the same color.
3. Do this for every color pair on the board.
4. **Every cell must be filled** — a level is only solved when all pairs are connected and the grid is completely covered.

Paths can be redrawn at any time. Drawing a new path over an existing one will truncate the old path at the crossing point. Dragging back over your own path removes the last step.

## Features

- **Procedurally generated levels** — every puzzle is unique, generated from a random seed. No two players get the same sequence of levels.
- **Scaling difficulty** — grid size and number of color pairs grow as you progress:
  - Levels 1–5 → 4×4 grid, 2–3 pairs
  - Levels 6–10 → 5×5 grid, 3–4 pairs
  - Levels 11–20 → 6×6 grid, 4–5 pairs
  - Level 21+ → 7×7 / 8×8 grid, 5–6 pairs
- **Timer** — each level has a time limit that scales with difficulty. The clock starts on your first move.
- **Scoring** — points awarded per level based on base score, time remaining, and move efficiency.
- **Leaderboard** — top 10 scores saved locally, identified by player name.
- **Progress persistence** — your level and score are saved automatically and restored on your next visit.
- **Undo / Reset / Skip** — controls to undo the last move, reset the current level, or skip ahead.
- **Background music** — toggleable from the header.
- **Single file** — the entire game is contained in one HTML file with no dependencies or server required.

## Scoring

| Component | Formula |
|---|---|
| Base points | 100 × level number |
| Time bonus | remaining seconds × 10 |
| Efficiency bonus | max(0, 200 − moves × 2) |

Stars on the win screen reflect how much time was left: ⭐⭐⭐ above 60%, ⭐⭐ above 30%, ⭐ otherwise.

## Controls

| Action | Input |
|---|---|
| Draw path | Click / tap and drag from a dot |
| Undo last step | Drag back over previous cell, or ↩ button |
| Reset level | ↺ button |
| Skip level | → button |
| Mute music | 🎵 button in header |
| Leaderboard | 🏆 button in header |

## Running the game

No build step, no server, no dependencies at runtime. Just open `flowgrid.html` in any modern browser:

```bash
open flowgrid.html
```

Or serve it statically with any HTTP server if needed.

## Versioning

This project uses [Semantic Versioning](https://semver.org/) and releases are automated via [semantic-release](https://github.com/semantic-release/semantic-release) on every push to `main`.

Commit messages follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

| Prefix | Effect |
|---|---|
| `fix:` | patch release (1.0.x) |
| `feat:` | minor release (1.x.0) |
| `feat!:` or `BREAKING CHANGE:` | major release (x.0.0) |
| `chore:`, `docs:`, `style:` | no release |

## License

MIT

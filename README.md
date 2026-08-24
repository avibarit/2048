# 2048

Exact classic clone of [2048](https://play2048.co/) built with pure vanilla HTML, CSS, and JavaScript.

## How to play

Open `index.html` directly in any modern browser (double-click or File → Open).

- Use **arrow keys** (or **WASD**) to slide tiles
- On touch devices, **swipe** on the board
- Merge identical tiles to create larger powers of two
- Reach **2048** to win (you can keep playing after)
- Fill the board with no more moves = Game Over
- **Best** score is stored in `localStorage`

## Files

| File | Purpose |
|------|---------|
| `index.html` | Page structure |
| `styles.css` | Classic colors, layout, animations |
| `game.js` | Pure logic + renderer + controls |
| `test-game-logic.js` | Node unit tests for core rules |
| `2048-spec.md` | Original requirements |

## Running tests

```bash
node test-game-logic.js
```

Tests cover:

- Sliding and merging (including merge-once-per-move)
- Score calculation and merge position metadata
- Random tile spawn (2/4 with 90/10)
- Win and lose detection
- No tile added / score change on invalid moves

## Behavior (classic rules)

- Starts with exactly **2** random tiles
- Only adds a tile after a **successful** move
- `4 2 2 2` left → `4 4 2` (merge once)
- Win overlay on 2048; **Keep going** continues play
- Game over when the board is full and no adjacent equals
- Full keyboard, touch swipe, New Game, score + best

No frameworks, no build step, zero runtime dependencies.

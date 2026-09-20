# Offline Chess

Chess for school computer labs and old PCs: play the computer or a friend on the same PC. It is **one HTML file** (`FingerFuel-Chess.html`). There is nothing to install, no internet is needed, and there are no libraries or servers.

**Runs on:** IE11, Chrome, Firefox and Edge. Not supported: IE8 to IE10.

Author: [github.com/animeshmahat](https://github.com/animeshmahat)

---

## Quick start

1. Copy `FingerFuel-Chess.html` to the computer (a USB stick is fine).
2. Double-click the file. It opens in the default browser.
3. Optional: right-click the file, choose *Send to > Desktop (create shortcut)*.

For a clean window without browser tabs, create a Chrome shortcut whose target ends with:

```
--app=file:///C:/Path/To/FingerFuel-Chess.html
```

---

## Modes

- **Play the computer**: 4 levels (Beginner, Easy, Medium, Hard). Choose White, Black or random. Includes hints and undo.
- **Two players**: two people on the same PC, with names and an optional "turn the board after every move".
- **Clock** (optional): 1, 3, 5, 10, 15 or 30 minutes, with or without an increment.
- **Start from FEN** (optional): begin from any valid position, useful for puzzles and teaching.

## Rules implemented

- Legal moves only, check and checkmate
- Castling (king and rook unmoved, empty path, not out of, through or into check)
- En passant
- Promotion, with a choice of piece (including underpromotion)
- Draws: stalemate, insufficient material, threefold repetition, fifty-move rule, agreement
- Loss on time (a draw if the opponent cannot checkmate at all)
- Resigning

---

## Interface

- Click a piece and then a target square, or drag and drop.
- Dots show legal moves, rings show captures; the last move and check are highlighted.
- Captured pieces and material lead are shown beside each player.
- Move list in standard notation; click any move to review that position. Moves are blocked while reviewing.
- Undo takes back your move and the computer's reply. In two-player mode it takes back one move.
- Board colours (green, brown, blue, gray) and piece style (symbols or letters).
- The page itself never scrolls. Only the move list scrolls, inside its own box.

## Keys

| Key | Action |
|---|---|
| `Left` / `Right` (or `Up` / `Down`) | Step back / forward through the game |
| `Home` / `End` | First / latest position |
| `Esc` | Deselect a piece or close a window |

---

## The computer

Levels 1 and 2 play with deliberate mistakes so beginners can win. Levels 3 and 4 search deeper and are limited by time, so they answer within about 1.5 seconds (Medium) or 2.5 seconds (Hard) even on slow PCs; the screen may pause briefly while Hard thinks. Levels 2 to 4 use a tiny opening book for variety. The computer avoids repeating positions when it is winning.

## Requirements and limits

- Pieces use the system's chess symbols (Segoe UI Symbol on Windows 7 and newer). If a machine shows boxes instead of pieces, choose **Letters** under *Pieces* in the New game window.
- No sound, no saving of games in progress, and no play between two computers (two-player mode is one shared screen).
- Not supported: IE8 to IE10.

---

## Where data is stored

Only your settings are saved. Everything stays in the browser on that computer (`localStorage`) and nothing is sent anywhere.

| Data | Key |
|---|---|
| Chess settings | `ffchess_settings` |

Clearing the browser's site data removes them.

---

## Troubleshooting

| Problem | What to do |
|---|---|
| Pieces show as boxes | Choose *Letters* under *Pieces* in the New game window. |
| Hard level feels slow | Use Medium, or set a clock, since the computer then thinks for less time. |

---

## How it was tested

- Move generation matches the standard reference move counts (castling, en passant, promotion, pins).
- 500 random games (about 84,000 moves) were compared move by move with an independent chess library: legal moves, notation, checkmate, stalemate, insufficient material, repetition and the fifty-move rule.
- The computer was self-played at every level to check that it only plays legal moves, and tested on mates, captures, stalemate avoidance and basic endgames.
- Driven in a real browser with real keystrokes and mouse actions, at window sizes from 2560x1440 down to 320x480, checking that nothing overflows or scrolls.
- The code uses no modern-only features, and was also run with those features switched off to imitate old browsers.
- Not yet tested on a physical Windows 7 or Internet Explorer machine, so please try it on your oldest PC first.

## License

Released under the [MIT License](LICENSE). Copyright (c) 2026 Animesh Mahat.

You are free to use, copy, modify and share this app, including in schools, as long as the copyright notice and license text are kept.

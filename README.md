# OfflineChess
An offline chess html app.

Just download open in a browser and play.

Modes

Play the computer with 4 levels (Beginner to Hard). You can play White, Black or random, and get hints and undo.
Two players on one PC, with names and an optional "turn the board after every move".
Both modes have an optional clock (1, 3, 5, 10, 15 or 30 minutes, with or without an increment).
You can also start from a FEN position, which is handy for puzzles.

Rules

Legal moves only, with check and checkmate.
Castling, with all its conditions.
En passant.
Promotion, with a choice of piece, including underpromotion.
Draws:
stalemate
not enough pieces to mate
threefold repetition
the fifty-move rule
draw by agreement
Loss on time (a draw if the opponent can't checkmate anyway) and resigning.

Interface

Click-to-move and drag-and-drop, with legal-move dots, last-move and check highlights, and captured pieces.
A move list you can click to review any position.
Left/right arrows, Home and End to step through moves.
Board colours and a letters-instead-of-symbols piece style.

Layout

The page never scrolls in either direction. The move list scrolls inside its own box.
The layout switches between side-by-side and stacked.
I tested 15 window sizes from 2560×1440 down to 320×480, including the dialogs. Nothing went outside the window at any size, and resizing mid-game keeps the game.

Testing

The move generator matches the standard reference counts for castling, en passant, promotion and pins.
500 random games (about 84,000 moves) matched an independent chess library move for move. That covered legal moves, notation, mate, stalemate, insufficient material, repetition and the fifty-move rule.
The computer:
plays only legal moves in self-play at every level
finds mates in one and takes a hanging queen
mated a random defender in 6 of 6 test games (queen, rook, and two queens vs king)
avoids stalemate in the tested position
Real-browser tests covered clicks, drags, promotion, undo, clocks, resigning and draws.
I fixed one real bug before sending: the computer could make a move after losing on time while it was thinking.

Things to know

It runs on IE11, Chrome and Firefox. IE8–10 are not supported, and Windows 7 machines that only have IE8 need a newer browser.
Pieces are drawn with the system's chess symbols (Windows 7 has them). If a machine shows boxes, choose "Letters" under Pieces in the New game window.
Hard can pause up to about 2.5 seconds per move on slow PCs.
There are no sounds, and a game in progress isn't saved if the window is closed.

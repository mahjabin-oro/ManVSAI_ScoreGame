# SCORE! Human vs AI Number-Grid Game

A desktop strategy game where you play a **Bingo-style number game against an AI opponent** that plans its moves with the **Minimax algorithm and alpha-beta pruning**.

<!-- Add a screenshot or short GIF of gameplay here -->

---

## How the game works

- You and the AI each get a hidden **N × N grid** of shuffled numbers. You choose the size, from **3×3 to 9×9**.
- Players take turns calling a number, and it gets crossed off on **both** grids.
- Each **completed row, column or diagonal** earns a letter of **S-C-O-R-E**.
- Completing a **3×2 or 2×3 block** earns a bonus.
- The first player to collect all five letters wins. You can also tie.
- At the end you can choose **"Show AI Grid"** to see the board the AI was playing with.

## The AI

The AI does not pick numbers at random. It:

- Uses **Minimax search with alpha-beta pruning** to look ahead at possible moves
- Scores each board with a **custom heuristic** that rewards nearly completed rows, columns, diagonals and 3×2 / 2×3 blocks, and prefers lines that are closer to being finished
- Uses **move ordering** to look at the most promising moves first, which makes the pruning more effective
- Has to plan around the fact that the numbers you call also change its own board

## Features

- Animated splash screen and main menu
- Choose your grid size at the start
- Sound effects for hovering, clicking, scoring and winning
- Custom fonts and background artwork
- Win, lose and tie screens with restart

## Tech stack

Python · Pygame · NumPy

## Run it

```bash
pip install pygame numpy
python MANvsAI.py
```

`bingo.py` is an earlier version of the same game.

## What I learned

Building a game-playing agent for a game with **two separate boards**, where every move changes both players' positions. This meant writing a heuristic that weighs immediate scoring chances against longer-term patterns, and keeping the search fast enough to feel responsive on larger grids.

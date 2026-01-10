---
layout: default
title: "Project 0: 2048"
nav_order: 2
---

# Project 0: 2048
{: .no_toc }

**Deadline: Monday, February 3rd, 11:59 PM PT.**

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Hard Mode Project
If you are a strong programmer, you might be interested in the hard mode version of this project. In the hard mode version, you'll solve the same problem as the standard version of this project, but there will be no handholding and you'll have to come up with the design yourself.

## Overview
In this mini-project, you'll get some practice with Java by creating a playable game of 2048. We've already implemented the graphics and user interaction code, so your job is to implement the logic of the game. You will only need to modify `GameLogic.java`.

## Using Git
It is important to commit your work frequently. The typical commands are:
* `git status`
* `git add <file>`
* `git commit -m "message"`
* `git push origin main`

## 2048 Rules: Basic Rules
* The game is played on a grid of squares containing numbered tiles.
* **Tilting:** Tiles slide in a chosen direction until they hit an edge or another tile.
* **Merging:** Sliding tiles can merge with tiles of the same value.
* **Scoring:** Merging tiles adds their new value to your score.
* **Game End:** The game ends when no moves are possible or a tile reaches 2048.

## Setup
### Getting the Skeleton Files
Follow the Assignment Workflow Guide to get the skeleton code in your `proj0/` directory. 

### File Structure
* `game2048logic/GameLogic.java` (The only file you modify)
* `game2048rendering/Main.java` (Run this to play the game)

---

## Task 1: Understanding Tilts
### Rules: Tilting
1. Two tiles of the same value merge into one tile containing double the initial number.
2. A tile that is the result of a merge will not merge again on that tilt.
3. When three adjacent tiles of the same number move, the leading two tiles merge.
4. Four adjacent tiles of the same number form two merged tiles (e.g., [4, 4, 4, 4] becomes [8, 8, X, X]).

---

## Task 2: Move Tile Up (No Merging)
Implement `moveTileUpAsFarAsPossible(int[][] board, int r, int c, int minR)` in `GameLogic.java`.
* Ignore `minR` and merging for now.
* Move the tile at `(r, c)` up through empty squares until it hits the top or another tile.

---

## Task 3: Merging Tiles
Modify `moveTileUpAsFarAsPossible` to handle merges.
* If the tile hits another tile of the same value, they merge.
* **Return Value:** Return `1 + row_index` where the merge happened. If no merge occurs, return `0`.

---

## Task 4: Merging Tiles up to MinR
Now use the `minR` parameter.
* `minR` represents the row index below which a tile cannot move or merge.
* This prevents "double merges" in a single tilt.

---

## Task 5: Tilt Column
Implement `tiltColumn(int[][] board, int x)`.
* This method tilts one entire column (at index `x`) upwards.
* Use `moveTileUpAsFarAsPossible` as a helper.

---

## Task 6: Tilt Up
Implement `tiltUp(int[][] board)`.
* This method tilts the entire board north by calling `tiltColumn` on every column.

---

## Task 7: Tilt in Four Directions
Implement `tilt(int[][] board, Side side)`.
* Generalize your logic to handle all four directions.
* **Tip:** Use the provided helper methods to rotate the board so you can always reuse your "Tilt Up" logic.

---

## Playing the Game
Run `Main.java` to test your implementation manually.

## Style
Your code will be checked for style (indentation, variable naming, etc.) in the autograder.

## Submission and Grading
### Velocity Limiting
{: .warning }
> This project has limited submission tokens (typically 4 per 24 hours). Rely on local tests in `TestTask2.java`, `TestTask3.java`, etc., before submitting.

### Grading Overview
Your grade is based on passing the autograder tests.

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

## Overview
In this project, you will implement the core logic of the game 2048. We have provided the graphics and user interaction code; your job is to handle the tile movement and merging rules in `GameLogic.java`. 

## 2048 Rules: Basic Rules
* **The Grid:** Played on a square grid. Each square is empty or contains a numbered tile.
* **Tilting:** The player tilts the board North, South, East, or West. All tiles slide until they hit an edge or another tile.
* **Merging:** When two tiles of the same value collide, they merge into one tile with double the value.
* **Ending:** The game ends when there are no available moves or a tile reaches the value 2048.

## Setup
### File Structure
The project is organized into two packages:
* **`game2048logic`**: Contains `GameLogic.java` (the only file you edit) and `MatrixUtils.java`.
* **`game2048rendering`**: Contains the GUI code (Board, Main, Side, Tile).

---

## Task 1: Understanding Tilts
![2048 Tilting Animation](/img/2048-example.gif)
The animation above shows a few tilt operations. Here are the full rules for when merges occur that are shown in the image above.
1. Two tiles of the same value merge into one tile with double the value.
2. **No Double Merges:** A tile that is the result of a merge will not merge again on that same tilt.
3. **Leading Merge:** If three adjacent tiles have the same value, the leading two tiles merge first.
4. **Double Pairs:** Four identical adjacent tiles will form two separate merged tiles (e.g., [4, 4, 4, 4] → [8, 8, X, X]).

## Task 2: Move Tile Up (No Merging)
Implement `moveTileUpAsFarAsPossible(int[][] board, int r, int c, int minR)`.
* Move the tile at `(r, c)` as far North as possible. 
* For this task, ignore the `minR` parameter and all merging rules.

## Task 3: Merging Tiles
Modify `moveTileUpAsFarAsPossible` to handle merges. 
* **Return Value:** If a merge occurs, return $1 + row\_index$ of the merge. If no merge occurs, return $0$.

## Task 4: Merging Tiles up to MinR
Update the method to respect the `minR` parameter. Tiles cannot move to or merge with a row higher than `minR`.

## Task 5: Tilt Column
Implement `tiltColumn(int[][] board, int x)`. 
* Tilt the entire column `x` upward.
* Use `moveTileUpAsFarAsPossible` as a helper. Update `minR` based on the return value to prevent illegal double merges.

## Task 6: Tilt Up
Implement `tiltUp(int[][] board)` to tilt the entire board North by calling `tiltColumn` for every column.

## Task 7: Tilt in Four Directions
Implement the general `tilt(int[][] board, Side side)` method. 
* Use the provided `rotateLeft` and `rotateRight` methods to rotate the board so that you can reuse your "Tilt Up" logic for any direction.

---

## Testing and Grading
### Velocity Limiting
{: .warning }
Submissions are limited. You receive **4 submission tokens** that regenerate every **24 hours**. Test your code locally using the provided JUnit tests (e.g., `TestTask2.java`) before submitting to Gradescope.

### Grading Breakdown
| Category | Weight |
| :--- | :--- |
| TestTask2 | 15% |
| TestTask3 | 20% |
| TestTask4 | 20% |
| TestTask5 | 8% |
| TestTask6 | 4% |
| TestTask7 | 8% |
| TestIntegration | 25% |

---
*Content adapted from the [UC Berkeley CS 61B Spring 2025 Project 0 Specification](https://sp25.datastructur.es/projects/proj0/).*
---
layout: default
title: "Project 0: 2048"
nav_order: 1
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
In this mini-project, you'll get some practice with Java by creating a playable game of 2048. We've already implemented the graphics and user interaction code for you, so your job is to implement the logic of the game.

### 2048 Rules: Basic Rules
2048 is played on a grid of squares. Each square can either be empty or contain a numbered tile.

1. **Tilting:** The player chooses a direction (using the arrow keys) to tilt the board. All tiles slide in that direction until there is no empty space left.
2. **Merging:** As a tile slides, it can merge with another tile of the same value.
3. **Scoring:** Each time two tiles merge, the player earns the number of points on the new tile.

---

## Task 1: Understanding Tilts
In this project, you'll implement the logic that tilts the board.

### Rules: Tilting
1. Two tiles of the same value merge into one tile containing double the initial number.
2. A tile that is the result of a merge will not merge again on that tilt.
3. When three adjacent tiles in the direction of motion have the same number, the leading two tiles merge.

---

## Task 2: Move Tile Up (No Merging)
In `GameLogic.java`, fill in the `moveTileUpAsFarAsPossible(int[][] board, int r, int c, int minR)` method. 

Remember that a tile can move up through empty squares, until the tile either reaches the top row, or the tile reaches an empty square with another tile directly above it.

```java
public static void moveTileUpAsFarAsPossible(int[][] board, int r, int c, int minR) {
    // Your code here
}

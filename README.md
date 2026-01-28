# Percolation Simulation

This Java project implements the **Percolation** model using a union-find data structure to efficiently determine whether a system percolates. The project is designed for educational purposes and is commonly used in algorithms courses to demonstrate **dynamic connectivity** problems.

---

## Overview

The percolation model simulates a **grid of sites** (open or blocked) and answers questions like:

- Does the system **percolate**? (Is there a path of open sites from the top to the bottom?)
- Is a site **full**? (Connected to the top row through open sites)
- How many sites are currently **open**?

This implementation uses the **Weighted Quick Union with Path Compression** algorithm (`WeightedQuickUnionUF`) for efficient connectivity checks.

---

## Features

- Grid of size `n x n` with **all sites initially blocked**.
- Open sites with the `open(row, col)` method.
- Check if a site is **open** or **full**:
  - `isOpen(row, col)` — returns true if the site is open.
  - `isFull(row, col)` — returns true if the site is connected to the top.
- Check if the system **percolates** with `percolates()`.
- Track the **number of open sites** with `numberOfOpenSites()`.
- Two virtual sites are used:
  - **Top virtual site** connected to the top row.
  - **Bottom virtual site** connected to the bottom row (used for percolation detection).

---

## API Methods

```java
Percolation(int n)               // Create n-by-n grid, all sites blocked
void open(int row, int col)       // Open site at (row, col)
boolean isOpen(int row, int col)  // Is site (row, col) open?
boolean isFull(int row, int col)  // Is site (row, col) full?
int numberOfOpenSites()           // Number of open sites
boolean percolates()              // Does the system percolate?

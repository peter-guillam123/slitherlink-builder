# Slitherlink Builder

A small workshop tool for making [Slitherlink](https://en.wikipedia.org/wiki/Slitherlink) puzzles by hand. Draw the loop you want, and it works out a clean set of clue numbers that has your loop as its one and only solution.

**Live:** https://peter-guillam123.github.io/slitherlink-builder/

## What it does

- Draw a single closed loop by clicking or dragging along the grid edges (it won't let the loop fork).
- **Populate numbers** fills every cell with its edge count; **Create unique puzzle** then thins the clues to the smallest set that still has exactly one solution.
- **Check unique** confirms a clue set is uniquely solvable; a rough **difficulty** read updates live as you edit.
- **Play this puzzle** opens it in the player (`play.html`) in a new tab — solve it with lines and crosses, get live clue feedback, and a "Reveal solution" worked out by the solver. The player also opens saved `.json` files directly. The answer is never embedded in the play link.
- Undo/redo, save & load a project, export a PNG, and a clean print/PDF layout.

## How it's built

One self-contained HTML file — no install, no dependencies, nothing leaves your machine. The grid is SVG; the solver (the part that checks whether a clue set has exactly one solution) runs in a Web Worker so the interface never freezes. It does real Slitherlink deduction — forced edges, vertex parity, and a union-find to reject loops that close too early — rather than blind trial and error, so a 6×6 generates in a few milliseconds.

## Running it locally

Just open `index.html` in any modern browser. No build step.

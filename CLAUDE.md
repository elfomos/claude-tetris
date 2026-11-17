# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

### Run the game
To run the Tetris game, you can serve the `index.html` file using a simple HTTP server. For example, using Python:
```bash
python3 -m http.server 8000
```
Then, open `http://localhost:8000` in your web browser.

## High-level Architecture

This project is a vanilla JavaScript implementation of Tetris, designed to run directly in a web browser without any build process or external dependencies.

*   **`index.html`**: Defines the main HTML structure, including the game canvas (`<canvas id="board">`), a side panel for scores and controls, and overlays for pause/game over states.
*   **`style.css`**: Provides the visual styling with a dark/retro arcade aesthetic.
*   **`game.js`**: Contains all the core game logic. This includes the board model (a 2D array), piece definitions, collision detection, piece rotation (with wall kicks), the game loop (using `requestAnimationFrame`), line clearing, scoring, level progression, and ghost piece mechanics.

The game relies heavily on the HTML5 Canvas 2D API for rendering and `requestAnimationFrame` for its game loop, ensuring synchronization with the browser's rendering cycle.

## Customization

Key game parameters can be adjusted by modifying constants within `game.js`. These include:
*   `COLS` and `ROWS`: Board dimensions.
*   `BLOCK`: Size of each block in pixels.
*   `COLORS`: Color palette for different pieces.
*   `LINE_SCORES`: Scoring values for clearing lines.
*   `dropInterval`: Initial speed of piece descent.

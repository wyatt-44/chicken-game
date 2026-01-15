# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Browser-based chicken farm and cooking game implemented as a single-file HTML application with embedded CSS and JavaScript.

## Development

No build system or package manager. Open `chicken-game.html` directly in a web browser to run.

## Architecture

Single HTML file with three sections:

1. **CSS (lines 7-559)**: Styling for farm visuals, kitchen elements, and animations
2. **HTML (lines 561-664)**: Game layout with HUD, farm, kitchen (inventory, stove, plates)
3. **JavaScript (lines 666-935)**: Game logic and state management

### Game State

Central `state` object tracks: caught/cooked/burned counts, score, 6-slot inventory array, selected slot, burner states (cooking flag, progress, interval), and active chicken elements.

### Core Mechanics

- **Chickens**: Spawn in farm area with random movement; click to catch and add to inventory
- **Cooking**: Select inventory slot, click burner to cook; progress 70-84% = perfect (+50), 85%+ = burned (-10), <70% = undercooked (returns to inventory)

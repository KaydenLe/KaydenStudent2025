---
layout: page
title: Tron
search_exclude: true
permalink: /tron/
---

## Overview

This is a simple text-based Tron game implemented in Python. The game consists of two players navigating a grid, leaving trails behind them. If a player runs into a trail, they lose the game.

### Game Features:
- 2 players (Player 1 and Player 2)
- A grid that displays the players and their trails
- Players lose if they collide with their own or their opponent's trail

## Python Code

```python
import os
import time

# Define the grid size
GRID_WIDTH = 20
GRID_HEIGHT = 10

# Define the players' positions and directions
player1_pos = [1, 1]
player2_pos = [GRID_WIDTH - 2, GRID_HEIGHT - 2]
player1_dir = (1, 0)  # Starts moving right
player2_dir = (-1, 0)  # Starts moving left

# Define the grid and players' trails
grid = [[' ' for _ in range(GRID_WIDTH)] for _ in range(GRID_HEIGHT)]
player1_trail = [player1_pos[:]]
player2_trail = [player2_pos[:]]

def clear_screen():
    os.system('cls' if os.name == 'nt' else 'clear')

def display_grid():
    clear_screen()
    for y in range(GRID_HEIGHT):
        for x in range(GRID_WIDTH):
            if [x, y] == player1_pos:
                print('1', end='')
            elif [x, y] == player2_pos:
                print('2', end='')
            elif [x, y] in player1_trail:
                print('+', end='')
            elif [x, y] in player2_trail:
                print('*', end='')
            else:
                print(' ', end='')
        print()
    print()

def update_position(pos, direction):
    return [(pos[0] + direction[0]) % GRID_WIDTH, (pos[1] + direction[1]) % GRID_HEIGHT]

def check_collision(pos, trail1, trail2):
    return pos in trail1 or pos in trail2

# Main game loop
def main():
    global player1_pos, player2_pos, player1_dir, player2_dir

    while True:
        # Update player positions
        player1_pos = update_position(player1_pos, player1_dir)
        player2_pos = update_position(player2_pos, player2_dir)

        # Check for collisions
        if check_collision(player1_pos, player1_trail, player2_trail):
            print("Player 2 Wins!")
            break
        if check_collision(player2_pos, player2_trail, player1_trail):
            print("Player 1 Wins!")
            break

        # Add new positions to trails
        player1_trail.append(player1_pos[:])
        player2_trail.append(player2_pos[:])

        # Display updated grid
        display_grid()

        # Wait for a short time before the next frame
        time.sleep(0.2)

if __name__ == "__main__":
    main()

# Snake with Wandering Food

A twist on the classic Snake game, built on the `snake.py` example from the
[freegames](https://grantjenks.com/docs/freegames/) package. In the original,
the food sits still until you eat it. Here the food wanders around the board,
so you have to chase it down.

## Requirements

- Python 3
- `tkinter` (comes with most Python installs; on some Linux distros you need
  to install it separately, e.g. `sudo apt install python3-tk`)
- [freegames](https://pypi.org/project/freegames/)

## Installation

```bash
git clone https://github.com/Dilosch03/python_snake.git
cd python_snake
pip install -r requirements.txt
```

## How to play

```bash
python snake.py
```

| Key | Action      |
| --- | ----------- |
| ↑   | Move up     |
| ↓   | Move down   |
| ←   | Move left   |
| →   | Move right  |

- Eat the food to grow. Your length is printed to the terminal each time you eat.
- The game ends when the snake hits a wall or its own body. The head turns red
  and the snake stops moving.

## What's different from the original

### The food moves

Each time the snake moves, the food also takes one step (10 px) up, down, left
or right, chosen at random. It never steps off the board.

The food **stops moving once the snake's head is right next to it**
(within about 1.5 tiles), so you can always catch it once you get close.

After you eat it, the food reappears at a random spot.

### Random colors

Each game picks two different colors for the snake and the food from black,
green, blue, purple and orange.

## How it works

All the logic is in [snake.py](snake.py):

- `moveFood(foodLoc)` picks random directions from `posible_movements` and takes
  the first one that keeps the food inside the board (checked with `inside()`).
- `move()` runs every 100 ms. It moves the snake, checks for collisions and
  eating, and calls `moveFood` only when the head is more than 15 px from the food.
- `snake_color` and `food_color` are chosen with `random.sample`, which
  guarantees the two colors are different.

## Ideas to try

The original freegames file suggests some exercises:

1. Make the snake faster or slower (change the `100` in `ontimer(move, 100)`).
2. Let the snake wrap around the edges instead of dying.
3. Make the snake respond to mouse clicks.

Snake (with Dynamic Food Movement)

An extended implementation of the classic Snake game based on Python's freegames module.

Gameplay Mechanics & Custom Behavior

In standard Snake, food remains stationary until consumed. In this version, the food actively wanders across the board unless the snake draws near.

Food Movement Logic

Evasion / Random Walk (moveFood): The food evaluates possible steps along the 4 cardinal directions (posible_movements). Using random.choices, it tests valid directions and commits to the first choice that remains

Large game trees would take up so much space and time to search until the game ends . So instead, fix the search depth to d, then when we reach depth d, approximate all the nodes using some heuristic, known as an evaluation function.

An evaluation function assigns a numerical score to a position without search further, estimating how good the position is.

Requirements:
- Provides a decent approximation (bad heuristics leads to weak strategy)
- Positions can be compared
- Higher value = easier to win
- Fast to compute
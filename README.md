# CI2024_lab3
Solve efficiently a genetic n^2 -1 puzzle (also known as Gem Puzzle, Boss Puzzle, Mystic Square etc.) using path-search algorithms

- Quality: number of actions in the solution
- Cost: total number of actions evaluated
- Efficiency: Quality vs Cost

## Tested Algorithms

Initially, I approached this problem using a breadth-first search (BFS), which explores every possible state at each step. While this method successfully solved the 3x3 puzzle within a feasible time frame, it struggled with larger puzzles. For instance, on the 4x4 puzzle, it failed to find a solution within an hour, leading me to terminate the program and seek an alternative approach.

I then implemented the A* algorithm, utilizing a priority queue. Each potential solution was added to the queue with a priority determined by \( G + H \), where \( G \) represents the actual cost of the path taken, and \( H \) is the estimated cost to the goal.

For the heuristic \( H \), I opted for the Manhattan distance, which measures the total movement required to align tiles with their target positions.

This approach proved more effective, solving the 4x4 puzzle in an average of 5 to 6 minutes. In some cases, it also managed to solve the 5x5 puzzle, depending on the complexity of the initial configuration.

Testing on larger dimensions was not conducted due to the exponential increase in computational requirements.

## Conclusion

The experiments demonstrate that while a breadth-first search is conceptually simple and guarantees an optimal solution, it is not feasible for puzzles larger than 3x3 due to the rapid growth of the state space. The A* algorithm, on the other hand, significantly improves performance by leveraging the Manhattan distance as a heuristic to guide the search, focusing on more promising states first.

Despite the improvements,even the A* algorithm also faces limitations as the puzzle size increases, with the 5x5 puzzle being solvable only in specific cases and larger dimensions becoming impractical. 

Future work could explore alternative heuristics or domain-specific optimizations


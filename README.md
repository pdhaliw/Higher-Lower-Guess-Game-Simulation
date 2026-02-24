# Higher-Lower-Guess-Game-Simulation
Simulation of the higher lower number guessing game popular online in February 2026.

# Number Guessing Strategy Simulation

This notebook analyzes multiple strategies for solving the number guessing game:

A number between 1 and N is selected.  
After each guess, feedback is given:
- "Higher" if the guess is too low  
- "Lower" if the guess is too high  

The process continues until the correct number is guessed.

---

## Method Descriptions

### Linear Search
Always guesses the lowest remaining number.  
Worst-case complexity: O(N).  
Deterministic strategy.

### Reverse Linear Search
Always guesses the highest remaining number.  
Worst-case complexity: O(N).  
Deterministic strategy.

### Random
Selects a random number within the current bounds.  
Expected complexity: O(N).  
High variance across runs.

### Binary Search
Always guesses the midpoint of the interval.  
Worst-case complexity: O(log₂N).  
Optimal deterministic strategy for uniformly distributed targets.

### Ternary Search
Splits the interval into thirds.  
Typically less efficient than binary search for this problem.

### Golden Ratio Search
Partitions the interval using an approximately 0.618 proportion.  
Inspired by numerical optimization methods.

### Noisy Midpoint
Uses the midpoint plus small random variation.  
Models imperfect human guessing.

### Step 25
Guesses in increments of 25 before refining the interval.  
Represents a simple stepping heuristic.

---

## Notebook Structure

This notebook supports two experimental modes.

### 1. Individual Method Runs

Each strategy can be executed independently using:

    run_method(...)

This produces a dataframe containing:
- method
- target_number
- guesses

These individual dataframes can later be combined using:

    pd.concat([...])

This approach is useful for evaluating standalone performance.

---

### 2. Shared Target Multi-Method Runs

All methods can be executed together using:

    run_all_methods_shared_target(...)

In this mode:
- Each run generates one random target number.
- All methods attempt that same number.
- Output includes:
    - run_number
    - target_number
    - method
    - guesses

This allows controlled comparison across strategies.





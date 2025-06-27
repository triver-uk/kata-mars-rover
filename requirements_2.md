## Requirements

The plateau may have obstacles, but luckily our rovers have an obstacle detection feature.
Before each move to a new square, the rover detects if an obstacle is present. If it is, it stops and reports the obstacle by prefixing `O:` to its last position before encountering the obstacle. For instance, `O:1:1:N` would mean that the rover encountered an obstacle at position `(1, 2)`.


## Examples


- Given a rover starting at `(0, 0)`, facing `N` and a grid with an obstacle at `(0, 3)`, input `MM` should output `0:2:N`
  - The rover moves North once, reaching `(0, 1)`
  - The rover moves North once more, reaching `(0, 2)`

- Given a rover starting at `(0, 0)`, facing `N` and a grid with an obstacle at `(0, 3)`, input `MMMMLMM` should output `O:0:2:N`
  - The rover moves North, reaching `(0, 1)`
  - The rover moves North, reaching `(0, 2)`
  - The rover cannot move North again because there is an obstacle on `(0, 3)` so instead it stops

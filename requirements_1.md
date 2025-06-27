## Requirements

- The plateau can be represented as a 10x10 grid
  - If a rover reaches the end of the grid, it wraps around (planets are spheres)
- A rover has state consisting of two parts:
  - its position on the grid (represented by an `(X, Y)` coordinate pair)
  - the compass direction it's facing (represented by a letter, one of `N` - North, `S` - South, `E` - East, `W` - West)
- The program input is a string of one-character move commands:
  - `L` and `R` rotate the direction the rover is facing (left and right respectively)
  - `M` moves the rover one grid square forward in the direction it is currently facing

The program's output is the final position of the rover after all the move commands have been executed. The position is represented as a coordinate pair and a direction, joined by colons to form a string.

## Examples

- Given a rover starting at `(0, 0)` and facing `N`, input `MM` should output `0:2:N`
  - The rover moves North once, reaching `(0, 1)`
  - The rover moves North once more, reaching `(0, 2)`

- Given a rover starting at `(0, 0)` and facing `N`, input `MMRMMLM` should output `2:3:N`
  - The rover moves North, reaching `(0, 1)`
  - The rover moves North, reaching `(0, 2)`
  - The rover rotates to the right, facing East
  - The rover moves East, reaching `(1, 2)`
  - The rover moves East, reaching `(2, 2)`
  - The rover rotates to the left, facing North
  - The rover moves North, reaching `(2, 3)`

- Given a rover starting at `(0, 0)` and facing `N`, and input `MMLMMLM` should output `8:1:S`
  - The rover moves North, reaching `(0, 1)`
  - The rover moves North, reaching `(0, 2)`
  - The rover rotates to the left, facing West
  - The rover moves West, reaching `(9, 2)` (because the grid wraps)
  - The rover moves West, reaching `(8, 2)`
  - The rover rotates to the left, facing South
  - The rover moves South, reaching `(8, 1)`

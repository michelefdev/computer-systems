# RGB Colors — Complements and Boolean Operations

## Color Encoding (Given)
Each color is represented as a 3-bit vector `(R, G, B)`:

| Color     | R | G | B | Bit Vector |
|-----------|---|---|---|------------|
| Black     | 0 | 0 | 0 | (0,0,0)    |
| Blue      | 0 | 0 | 1 | (0,0,1)    |
| Green     | 0 | 1 | 0 | (0,1,0)    |
| Cyan      | 0 | 1 | 1 | (0,1,1)    |
| Red       | 1 | 0 | 0 | (1,0,0)    |
| Magenta   | 1 | 0 | 1 | (1,0,1)    |
| Yellow    | 1 | 1 | 0 | (1,1,0)    |
| White     | 1 | 1 | 1 | (1,1,1)    |

---

## A. Complements of the Eight Colors

_Complement rule_: flip each bit (0 → 1, 1 → 0)

| Color     | Original (R,G,B) | Complement (R,G,B) | Complement Color |
|-----------|------------------|--------------------|------------------|
| Black     | (0,0,0)          | (1,1,1)            | White            |
| Blue      | (0,0,1)          | (1,1,0)            | Yellow           |
| Green     | (0,1,0)          | (1,0,1)            | Magenta          |
| Cyan      | (0,1,1)          | (1,0,0)            | Red              |
| Red       | (1,0,0)          | (0,1,1)            | Cyan             |
| Magenta   | (1,0,1)          | (0,1,0)            | Green            |
| Yellow    | (1,1,0)          | (0,0,1)            | Blue             |
| White     | (1,1,1)          | (0,0,0)            | Black            |

---

## B. Boolean Operations on Colors (Setup Only)

_Boolean operations are applied bitwise to the RGB vectors._

### OR (`|`)
- Blue `|` Green
  011 -> Cyan

---

### AND (`&`)
- Yellow `&` Cyan
  010 -> Green
---

### XOR (`^`)
- Red `^` Magenta
  001 -> Blu
---
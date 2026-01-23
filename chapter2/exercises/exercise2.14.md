# Exercise 2.14 — Bitwise and Logical Operations

Given: `x = 0x66` and `y = 0x39`

## Solution

### Bitwise Operations

| Expression | Binary Calculation | Value |
|---|---|---|
| `x & y` | 0110 0110 & 0011 1001 | **0x20** |
| `x \| y` | 0110 0110 \| 0011 1001 | **0x7F** |
| `~x \| ~y` | 1001 1001 \| 1100 0110 | **0xDF** |
| `x & !y` | 0x66 & 0 (since y is non-zero) | **0x00** |

### Logical Operations

| Expression | Evaluation | Value |
|---|---|---|
| `x && y` | Both non-zero → true | **1** |
| `x \|\| y` | At least one non-zero → true | **1** |
| `!x \|\| !y` | (!non-zero) \|\| (!non-zero) = 0 \|\| 0 | **0** |
| `x && ~y` | x non-zero && ~0x39 = 0xC6 non-zero → true | **1** |

## Notes

- In C, bitwise operations (`&`, `|`, `~`) work on individual bits
- Logical operations (`&&`, `||`, `!`) treat non-zero as true and zero as false, returning 0 or 1
- `!y` is 0 because y (0x39) is non-zero
- `~y` is the bitwise complement: `~0x39 = 0xC6`

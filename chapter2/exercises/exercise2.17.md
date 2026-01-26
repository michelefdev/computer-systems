# Exercise 2.17 — Unsigned and Two's-Complement Interpretations

Assuming w = 4, assign a numeric value to each possible hexadecimal digit under unsigned (B2U_4) or two's-complement (B2T_4) interpretation.

## Table

| Hexadecimal | Binary | B2U_4(x) | B2T_4(x) |
|-------------|--------|----------|----------|
| 0xE | 1110 | 14 | -2 |
| 0x0 | 0000 | 0 | 0 |
| 0x5 | 0101 | 5 | 5 |
| 0x8 | 1000 | 8 | -8 |
| 0xD | 1101 | 13 | -3 |
| 0xF | 1111 | 15 | -1 |

## Notes

- For B2U_4: Write out the nonzero powers of two in the summation (Equation 2.1)
- For B2T_4: Write out the nonzero powers of two in the summation (Equation 2.3)
- Remember: For two's-complement with w=4, the most significant bit has weight -2³ = -8

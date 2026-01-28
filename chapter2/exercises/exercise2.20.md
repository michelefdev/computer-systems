# Exercise 2.20 — Applying Equation 2.6 to T2U_4

Equation 2.6 describes the Two's-Complement to Unsigned conversion function:

```
T2U_w(x) = {  x + 2^w,  x < 0
           {  x,        x ≥ 0
```

## Verification with T2U_4 Table

For w = 4, we have 2^w = 2^4 = 16. Let's verify each entry from the T2U_4 table:

### Negative Values (x < 0)
For negative two's complement values, we apply: T2U_4(x) = x + 16

| x | x + 16 | T2U_4(x) | Match? |
|---|--------|----------|--------|
| −8 | −8 + 16 = 8 | 8 | ✓ |
| −3 | −3 + 16 = 13 | 13 | ✓ |
| −2 | −2 + 16 = 14 | 14 | ✓ |
| −1 | −1 + 16 = 15 | 15 | ✓ |

### Non-Negative Values (x ≥ 0)
For non-negative values, we apply: T2U_4(x) = x

| x | T2U_4(x) | Match? |
|---|----------|--------|
| 0 | 0 | ✓ |
| 5 | 5 | ✓ |

## Analysis

Equation 2.6 perfectly describes the conversion pattern observed in the table:

1. **For negative two's complement values** (−8, −3, −2, −1): The function adds 2^w = 16 to the signed value to produce the unsigned equivalent. This works because in w-bit two's complement, the negative value x represents x + 2^w as an unsigned value.

2. **For non-negative values** (0, 5): The function simply returns the value as-is, since the bit pattern is identical in both two's complement and unsigned representations.

3. **Range observation**: The maximum negative value in 4-bit two's complement is −8, which converts to 8 in unsigned. The maximum positive value is 7 (not shown in this table), which would remain 7. Values range from 0 to 15 in unsigned representation, which is the full range of 4-bit values.

This equation encapsulates the fundamental principle that converting a negative two's complement number to unsigned is equivalent to adding 2^w to restore the correct magnitude in the unsigned interpretation.

# Exercise 2.21 — Casting and Relational Operations

Assuming the expressions are evaluated on a 32-bit machine that uses two's-complement arithmetic, fill in the following table describing the effect of casting and relational operations, in the style of Figure 2.18:

## Casting and Relational Operations Table

| Expression | Type | Evaluation | Reasoning |
|---|---|---|---|
| `-2147483647-1 == 2147483648U` | unsigned | 1 | same bit array |
| `-2147483647-1 < 2147483647` | signed | 1 | signed comparison |
| `-2147483647-1U < 2147483647` | unsigned | 0 | cast to unsigned|
| `-2147483647-1 < -2147483647` | signed | 1 | normal comparison|
| `-2147483647-1U < -2147483647` | unsigned | 1 | double cast to unsigned|

## Notes

- The value `-2147483647-1` is the minimum 32-bit signed integer (INT_MIN)
- The value `2147483648U` exceeds the maximum 32-bit signed integer by 1
- When mixing signed and unsigned integers in comparisons, implicit casting occurs
- Pay attention to how two's-complement representation affects the comparison results

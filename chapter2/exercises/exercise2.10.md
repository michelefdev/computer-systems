# XOR Swap Step-by-Step Analysis

Consider the following program that swaps two integers using XOR:

```c
void inplace_swap(int *x, int *y) {
    *y = *x ^ *y; /* Step 1 */
    *x = *x ^ *y; /* Step 2 */
    *y = *x ^ *y; /* Step 3 */
}
```

Unlike the usual swapping technique, this method does not use a temporary variable.
Starting with values `a` and `b` in the locations pointed to by `x` and `y`, fill in the table below, showing the values after each step.

Recall that for any bit vector `a`, `a ^ a = 0` and `a ^ 0 = a`.

| Step       | `*x`                   | `*y`         |
|------------|-----------------------|-------------|
| Initially  | a                     | b           |
| Step 1     | a                     | a ^ b       |
| Step 2     | a ^ (a ^ b)           | a ^ b       |
|            | (a ^ a) ^ b           |             |
|            | 0 ^ b                 |             |
|            | b                     |             |
| Step 3     | b                     | b ^ (a ^ b) |
|            | b                     | b ^ a ^ b   |
|            | b                     | (b ^ b) ^ a |
|            | b                     | 0 ^ a       |
|            | b                     | a           |
| Finally    | b                     | a           |

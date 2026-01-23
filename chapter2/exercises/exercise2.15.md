# Exercise 2.15 — Equality Comparison Using Bit-Level Operations

## Problem

Using only bit-level and logical operations, write a C expression that is equivalent to `x == y`.
The expression should return 1 when `x` and `y` are equal, and 0 otherwise.

## Solution

The expression is: `!(~(~x ^ y))`

Or more simply: `!(x ^ y)`

### Explanation

The key insight is that the XOR operation (`^`) returns 0 when bits are equal and 1 when they differ.

- When `x == y`: every bit position has the same value, so `x ^ y = 0`, and `!(x ^ y) = 1`
- When `x != y`: at least one bit position differs, so `x ^ y ≠ 0`, and `!(x ^ y) = 0`

### Worked Examples

#### Example 1: x ≠ y

```
x = 100101 (37 in decimal)
y = 100100 (36 in decimal)

x ^ y = 000001 (bits differ in position 0)
!(000001) = 0  ✓
```

#### Example 2: x == y

```
x = 100101 (37 in decimal)
y = 100101 (37 in decimal)

x ^ y = 000000 (all bits are equal)
!(000000) = 1  ✓
```

#### Example 3: x ≠ y

```
x = 100100 (36 in decimal)
y = 100101 (37 in decimal)

x ^ y = 000001 (bits differ in position 0)
!(000001) = 0  ✓
```

## C Implementation

```c
int equals(int x, int y) {
    return !(x ^ y);
}
```

This uses only the XOR (`^`) and logical NOT (`!`) operators, as required.

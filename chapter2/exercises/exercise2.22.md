# Exercise 2.22

Show that each of the following bit vectors is a two's-complement representation of −5 by applying Equation 2.3:

**A. [1011]**

**B. [11011]**

**C. [111011]**

Observe that the second and third bit vectors can be derived from the first by sign extension.

---

## Solution

Using Equation 2.3, the two's-complement value of a bit vector is:

```
B2T_w(x) = -x_(w-1) * 2^(w-1) + Σ(i=0 to w-2) x_i * 2^i
```

where x_(w-1) is the sign bit (most significant bit) and w is the width.

### A. [1011] (4 bits)

```
B2T_4([1011]) = -1 * 2^3 + 0 * 2^2 + 1 * 2^1 + 1 * 2^0
              = -8 + 0 + 2 + 1
              = -5 ✓
```

### B. [11011] (5 bits)

```
B2T_5([11011]) = -1 * 2^4 + 1 * 2^3 + 0 * 2^2 + 1 * 2^1 + 1 * 2^0
               = -16 + 8 + 0 + 2 + 1
               = -5 ✓
```

### C. [111011] (6 bits)

```
B2T_6([111011]) = -1 * 2^5 + 1 * 2^4 + 1 * 2^3 + 0 * 2^2 + 1 * 2^1 + 1 * 2^0
                = -32 + 16 + 8 + 0 + 2 + 1
                = -5 ✓
```

### Sign Extension

Note that [11011] is derived from [1011] by prepending a 1 (the sign bit), and [111011] is derived from [11011] by prepending another 1. This is **sign extension**: when extending a negative number in two's-complement representation, we replicate the sign bit on the left.

When we add leading 1s:
- From [1011] to [11011]: The added bit contributes +1 * 2^4 = +16, but the sign bit contribution changes from -1 * 2^3 = -8 to -1 * 2^4 = -16 (a decrease of -8). Net change: 16 - 8 = 8, which is exactly offset by rearrangement of bits.
- From [11011] to [111011]: The added bit contributes +1 * 2^5 = +32, but the sign bit contribution changes from -1 * 2^4 = -16 to -1 * 2^5 = -32 (a decrease of -16). Net change: 32 - 16 = 16, again offset.

This demonstrates that sign extension preserves the numeric value in two's-complement representation.

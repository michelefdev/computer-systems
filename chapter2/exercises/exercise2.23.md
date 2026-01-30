# Exercise 2.23

Consider the following C functions:

```c
int fun1(unsigned word) {
    return (int) ((word << 24) >> 24);
}

int fun2(unsigned word) {
    return ((int) word << 24) >> 24;
}
```

Assume these are executed on a machine with a 32-bit word size that uses two's-complement arithmetic. Assume also that right shifts of signed values are performed arithmetically, while right shifts of unsigned values are performed logically.

## Part A

Fill in the following table showing the effect of these functions for several example arguments. You will find it more convenient to work with a hexadecimal representation. Just remember that hex digits 8 through F have their most significant bits equal to 1.

| w | fun1(w) | fun2(w) |
|---|---------|---------|
| 0x00000076 | 0x00000076 | 0x00000076 |
| 0x87654321 | 0x00000021 | 0x00000021 |
| 0x000000C9 | 0x000000C9 | 0xffffffC9 |
| 0xEDCBA987 | | |

## Solution

### Part A

| w | fun1(w) | fun2(w) |
|---|---------|---------|
| 0x00000076 | | |
| 0x87654321 | | |
| 0x000000C9 | | |
| 0xEDCBA987 | | |

**Analysis:**

TODO: Explain the behavior of fun1 and fun2 for each input value.

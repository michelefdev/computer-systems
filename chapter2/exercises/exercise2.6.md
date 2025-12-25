# Exercise 2.6 — show_int vs show_float (Bit Patterns)

Using `show_int` and `show_float`, we determine:
- Integer 3510593 → hex `0x00359141`
- Floating-point 3510593.0 → hex `0x4A564504`

## A) Binary Representations

- 3510593 (`0x00359141`):
```
0000 0000 0011 0101 1001 0001 0100 0001
```

- 3510593.0 (`0x4A564504`):
```
0100 1010 0101 0110 0100 0101 0000 0100
```

## B) Shift to Maximize Matching Bits

Align the two bit strings to maximize overlap:
```
INT   00000000001101011001000101000001
FLOAT   01001010010101100100010100000100

Shifted alignment (showing the common run):
INT     0000000000110 1011001000101000001
FLOAT     01001010010 1011001000101000001 00
```
- Matching bits: 19

## C) Non-matching Parts

- High-order bits do not match: `INT` begins with zeros, while `FLOAT` has the IEEE-754 sign+exponent field (`01001010...`).
- Low-order tail does not fully match due to alignment and extra trailing bits on `FLOAT` (`...00`).
- In short, the middle run matches; the leading and trailing segments differ.

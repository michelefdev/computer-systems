# Exercise 2.16 — Shift Operations

Fill in the table below showing the effects of the different shift operations on single-byte quantities. The best way to think about shift operations is to work with binary representations. Convert the initial values to binary, perform the shifts, and then convert back to hexadecimal. Each of the answers should be 8 binary digits or 2 hexadecimal digits.

## Solution Table

| x (Hex) | x >> 2 (Logical) | | x << 3 | | x >> 2 (Arithmetic) | |
|---|---|---|---|---|---|---|
| | Binary | Hex | Binary | Hex | Binary | Hex |
| 0xC3 |0011 0000 |0x30 | | | | |
| 0x75 |0001 1101 |0x1D | | | | |
| 0x87 |0010 0001 |0x21 | | | | |
| 0x66 |0001 1001 |0x19 | | | | |

## Instructions

1. Convert each hex value to 8-bit binary
2. For **x >> 2 (Logical)**: Right shift by 2, fill left with 0s
3. For **x << 3**: Left shift by 3, fill right with 0s
4. For **x >> 2 (Arithmetic)**: Right shift by 2, fill left with sign bit (MSB)
5. Convert results back to hexadecimal

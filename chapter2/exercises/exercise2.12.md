# Exercise 2.12 — Bit-Level C Expressions

**Objective**
- Write C expressions, in terms of variable `x`, that compute the requested values without assuming a fixed word size. Expressions must work for any word size $w \ge 8$.

**Problem**
- A. The least significant byte of `x`, with all other bits set to 0. [Expected for `x = 0x87654321`, `w = 32`: `0x00000021`]
- B. All but the least significant byte of `x` complemented, with the least significant byte left unchanged. [Expected: `0x789ABC21`]
- C. The least significant byte set to all 1s, and all other bytes of `x` left unchanged. [Expected: `0x876543FF`]

### A.
#### Solution
The solution is `x & 0x000000ff`
#### Test
0x87654321
1000 0111 0110 0101 0100 0011 0010 0001 x 
0000 0000 0000 0000 0000 0000 1111 1111 0x000000ff
0000 0000 0000 0000 0000 0000 0010 0001 x & 0x000000ff


### B.
0x87654321
1000 0111 0110 0101 0100 0011 0010 0001 x
0111 1000 1001 1010 1011 1100 1101 1110 ~x
1111 1111 1111 1111 1111 1111 0000 0000 ~0x000000ff
0111 1000 1001 1010 1011 1100 0000 0000 (~x & ~0x000000ff)

0000 0000 0000 0000 0000 0000 0010 0001 (x & 0x000000ff)

0111 1000 1001 1010 1011 1100 0010 0001 [(~x & ~0x000000ff) | (x & 0x000000ff)]


### C.
0x87654321
1000 0111 0110 0101 0100 0011 0010 0001 x
0000 0000 0000 0000 0000 0000 1111 1111 0x000000ff
1000 0111 0110 0101 0100 0011 1111 1111 (x | 0x000000ff )

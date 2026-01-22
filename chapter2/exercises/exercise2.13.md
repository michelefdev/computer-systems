# Exercise 2.13 — `bis` / `bic` (solution)

The Digital Equipment VAX provided the bit-manipulation instructions `bis` (bit set)
and `bic` (bit clear). Both take a data word `x` and a mask word `m`.

- `bis(x,m)` sets to 1 every bit in `x` where `m` has a 1 (i.e. sets bits indicated by `m`).
- `bic(x,m)` clears to 0 every bit in `x` where `m` has a 1 (i.e. clears bits indicated by `m`).

We want to implement the usual bitwise operators `|` and `^` using only `bis` and `bic`.

Observations:

- `bis(x,y)` sets the bits of `x` where `y` has 1s, so

	bis(x,y) = x | y

- For XOR, use the identity

	x ^ y = (x & ~y) | (y & ~x)

	Notice `bic(x,y)` clears bits of `x` where `y` has 1s, so `bic(x,y) = x & ~y`.
	Therefore

	bis(bic(x,y), bic(y,x)) = (x & ~y) | (y & ~x) = x ^ y

Example (5-bit words):

- Let `x = 10001`
- Let `y = 10100`

Compute OR (via `bis`):

- `bis(x,y) = x | y = 10101`

Compute XOR (via `bic` then `bis`):

- `bic(x,y) = x & ~y = 10001 & 01011 = 00001`
- `bic(y,x) = y & ~x = 10100 & 01110 = 00100`
- `bis(00001, 00100) = 00101` which equals `x ^ y`.

Implementations (using only `bis` and `bic`):

```c
unsigned OR(unsigned x, unsigned y) {
		return bis(x, y); /* equivalent to x | y */
}

unsigned XOR(unsigned x, unsigned y) {
		return bis(bic(x, y), bic(y, x)); /* equivalent to x ^ y */
}
```

Thus `bis` directly implements bitwise OR, and combining `bic` with `bis` implements XOR.







# Powers of Two in Hexadecimal

This note turns the observation “2^n is a 1 followed by n zeros in binary” into a quick method to write 2^n directly in hexadecimal by aligning to 4-bit groups (nibbles).

## Binary Pattern

- 2^n in binary: `1` followed by `n` zeros.
- Examples:

```
2^1  = 10
2^2  = 100
2^3  = 1000
2^4  = 10000
2^5  = 100000
2^6  = 1000000
2^7  = 10000000
2^8  = 100000000
2^9  = 1000000000
2^10 = 10000000000
2^11 = 100000000000
```

## Align to Nibbles (Hex)

Let n = 4j + i with i ∈ {0, 1, 2, 3}.
- Group the binary into 4-bit nibbles from the right.
- The leftmost (possibly incomplete) nibble is padded with leading zeros.
- The first nibble and the number of trailing all-zero nibbles determine the hex form.

Mapping for the leading nibble:
- i = 0 → leading nibble `0001` → leading hex digit `1`
- i = 1 → leading nibble `0010` → leading hex digit `2`
- i = 2 → leading nibble `0100` → leading hex digit `4`
- i = 3 → leading nibble `1000` → leading hex digit `8`

After that leading nibble, there are exactly `j` nibbles of `0000` (i.e., `j` hex zeros).

Therefore:
- Hex form of 2^n is one of `1, 2, 4, 8` followed by `j` hex zeros.
- Compactly: 2^n = h × 16^j with h ∈ {1, 2, 4, 8} and n = 4j + i mapping to h as above.

## Quick Examples

- n = 5 → 2^5: n = 4·1 + 1 → leading `2`, then 1 hex zero → `0x20`.
- n = 7 → 2^7: n = 4·1 + 3 → leading `8`, then 1 hex zero → `0x80`.
- n = 9 → 2^9: n = 4·2 + 1 → leading `2`, then 2 hex zeros → `0x200`.
- n = 10 → 2^10: n = 4·2 + 2 → leading `4`, then 2 hex zeros → `0x400`.
- n = 11 → 2^11: n = 4·2 + 3 → leading `8`, then 2 hex zeros → `0x800`.
- n = 12 → 2^12: n = 4·3 + 0 → leading `1`, then 3 hex zeros → `0x1000`.
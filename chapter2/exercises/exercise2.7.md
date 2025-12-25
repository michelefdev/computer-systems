# Exercise 2.7 — show_bytes with strlen

What would be printed as a result of the following call to `show_bytes`?

```c
const char *s = "abcdef";
show_bytes((byte_pointer) s, strlen(s));
```

Answer (hex bytes):
```
61 62 63 64 65 66
```

Explanation:
- `strlen(s)` returns the number of characters before the terminating null byte `\0`, so for `"abcdef"` it returns 6.
- The actual in-memory representation of the string is the six character bytes followed by a null terminator: `61 62 63 64 65 66 00`.
- Since `show_bytes` is called with length `strlen(s)`, it prints only the first 6 bytes and does not include the trailing `00`.
- Each byte is the ASCII code (in hex) of the corresponding character. Because we’re printing from a `char*`, endianness does not affect the order of these bytes.

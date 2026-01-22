# Exercise 2.5 — show_bytes and Endianness

Consider the following three calls to `show_bytes`:

```c
int val = 0x87654321;
typedef unsigned char *byte_pointer;
byte_pointer valp = (byte_pointer) &val;
show_bytes(valp, 1); /* A. */
show_bytes(valp, 2); /* B. */
show_bytes(valp, 3); /* C. */
```

| Case | Bytes Shown | Little Endian Output | Big Endian Output |
|-----:|-------------|----------------------|-------------------|
| A    | 1 byte      | 21                   | 87                |
| B    | 2 bytes     | 21 43                | 87 65             |
| C    | 3 bytes     | 21 43 65             | 87 65 43          |

For context, the implementation of `show_bytes`:

```c
#include <stdio.h>

typedef unsigned char *byte_pointer;

void show_bytes(byte_pointer start, int len) {
    int i;
    for (i = 0; i < len; i++)
        printf(" %.2x", start[i]);
    printf("\n");
}
```

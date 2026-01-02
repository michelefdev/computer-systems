# Reverse Array Analysis

You are given the following function for reversing an array using `inplace_swap`:

```c
void reverse_array(int a[], int cnt) {
    int first, last;
    for (first = 0, last = cnt-1; first <= last; first++, last--)
        inplace_swap(&a[first], &a[last]);
}
```

When applied to an array of even length, the function works correctly.
However, for an array of odd length, the middle element becomes `0`.

---

## Questions

### A. For an array of odd length `cnt = 2k + 1`, what are the values of variables `first` and `last` in the final iteration of function `reverse_array`?

**Answer:**

For an odd-length array `cnt = 2k + 1`, the function:

```c
void reverse_array(int a[], int cnt) {
    int first, last;
    for (first = 0, last = cnt-1; first <= last; first++, last--)
        inplace_swap(&a[first], &a[last]);
}
```

- Loop variables start: `first = 0`, `last = cnt - 1`
- They move: `first++`, `last--`
- Equality (middle) point: `first = last = (cnt - 1)/2`
- After last iteration: `first = (cnt-1)/2 + 1`, `last = (cnt-1)/2 - 1`
- Loop terminates when `first > last`. This explains why the middle element is affected in odd-length arrays.


---

### B. Why does this call to function `xor_swap` set the array element to 0?

**Answer:**

Recall the function used from the previous exercise:

```c
void inplace_swap(int *x, int *y) {
    *y = *x ^ *y; /* Step 1 */
    *x = *x ^ *y; /* Step 2 */
    *y = *x ^ *y; /* Step 3 */
}
```

When this function is called on an array of odd length, the final iteration of the loop applies the swapping algorithm to the *same element*. In other words, both pointers refer to the same memory address.

To see why this causes a problem, consider a simple example. Assume the array starts at address `0x100`:

```
a = [1, 2, 3]
```

In the last iteration of `reverse_array`, the function call becomes:

```
inplace_swap(&a[1], &a[1])
```

Both pointers refer to the same element. The state of the variables is therefore:

| Step   | `*x` | `*y` | `&x`   | `&y`   |
|--------|------|------|--------|--------|
| Step 0 | 2    | 2    | 0x101  | 0x101  |
| Step 1 | 0    | 0    | 0x101  | 0x101  |

Since `x` and `y` point to the same location, Step 1 computes `*x ^ *x`, which evaluates to `0`. This value is written back to that same memory location. As a result, the middle element of the array is overwritten with `0`.

This explains why the algorithm fails for arrays of odd length.
### C. What simple modification to the code for `reverse_array` would eliminate this problem?

**Answer:**

A simple fix is to change the loop’s exit condition from `<=` to `<`.
This prevents the function from attempting to swap the middle element of an odd-length array with itself.

```c
void reverse_array(int a[], int cnt) {
    int first, last;
    for (first = 0, last = cnt - 1; first < last; first++, last--)
        inplace_swap(&a[first], &a[last]);
}
```

With this modification, the algorithm works correctly for both odd- and even-length arrays.

---

## Example: Odd-Length Array (`cnt = 5`)

Initial array:

```
[1, 2, 3, 4, 5]
```

| First | Last | Cnt | Array before     | Array after          |
|-----:|-----:|----:|------------------|----------------------|
| 0     | 4    | 5   | [1,2,3,4,5]      | [5,2,3,4,1]          |
| 1     | 3    | 5   | [5,2,3,4,1]      | [5,4,3,2,1]          |
| 2     | 2    | 5   | [5,4,3,2,1]      | (no swap) [5,4,3,2,1]|

The loop stops before `first == last`, so the middle element (`3`) is never swapped with itself.

---

## Example: Even-Length Array (`cnt = 4`)

Initial array:

```
[1, 2, 3, 4]
```

| First | Last | Cnt | Array before  | Array after                 |
|-----:|-----:|----:|---------------|-----------------------------|
| 0     | 3    | 4   | [1,2,3,4]     | [4,2,3,1]                   |
| 1     | 2    | 4   | [4,2,3,1]     | [4,3,2,1]                   |
| 2     | 1    | 4   | [4,3,2,1]     | (loop terminates) [4,3,2,1] |
The algorithm behaves correctly for even-length arrays as well.

---

This change eliminates the incorrect zeroing of the middle element while preserving correct behavior in all cases.
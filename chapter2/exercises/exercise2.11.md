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

<!-- Your answer here -->

---

### B. Why does this call to function `xor_swap` set the array element to 0?

**Answer:**

When calling the function on an odd-numbered n-length array, the last iteration ofthe cycle apply the swapping algorithm on the same number, pointing to the same address. So the first

---

### C. What simple modification to the code for `reverse_array` would eliminate this problem?

**Answer:**

<!-- Your answer here -->
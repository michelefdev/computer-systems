# Boolean Logic — Sets and Bit Vectors

This note connects set operations to bitwise operations on their characteristic (indicator) vectors. The core idea: performing set operations (intersection, union) corresponds exactly to applying bitwise operations (AND, OR) on the vectors.

## Quick Setup and Examples

- `w = 3`
- `A = {0, 1, 2}`
- Characteristic vector (length 3): `a = [1, 1, 1]`

---

Using a single byte (8-bit) universal set `U = {0, 1, 2, 3, 4, 5, 6, 7}`:

- `A = {0, 3, 5, 6}` (so `A ⊆ U`)
	- Characteristic vector: `a = [0 1 1 0 1 0 0 1]`
- `B = {0, 2, 4, 6}` (so `B ⊆ U`)
	- Characteristic vector: `b = [0 1 0 1 0 1 0 1]`

Note: We can choose the “superset” (universal set) size as large as we want. Here, 8 bits make a single byte, which is convenient.

---

### Operations

- Intersection: `A ∩ B = {0, 6}`
	- Bitwise: `a & b = [0 1 0 0 0 0 0 1]`

- Union: `A ∪ B = {0, 2, 3, 4, 5, 6}`
	- Bitwise: `a | b = [0 1 1 1 1 1 0 1]`

Observation: The results from set operations match the results from the corresponding bitwise operations on the characteristic vectors.

---

## Characteristic Vectors (Definition)

Let `U = {0, 1, 2, …, n}` be the universal set, and let `A` and `B` be subsets of `U`.

- The characteristic vector of `A` is defined as: `a[i] = 1` if `i ∈ A`, and `a[i] = 0` if `i ∉ A`, for every `0 ≤ i ≤ n`.
- The characteristic vector of `B` is defined analogously: `b[i] = 1` if `i ∈ B`, and `b[i] = 0` otherwise.

## Proof: Intersection ↔ Bitwise AND

Let `C = A ∩ B`. We show that the characteristic vector `c` of `C` equals the bitwise AND of `a` and `b`.

- Case `c[i] = 1`:
	- Then `i ∈ C`, hence `i ∈ A` and `i ∈ B`.
	- By definition, `a[i] = 1` and `b[i] = 1`.
	- Therefore, `(a[i] AND b[i]) = 1 AND 1 = 1`, matching `c[i]`.

- Case `c[i] = 0`:
	- Then `i ∉ C`, which means not both `i ∈ A` and `i ∈ B`.
	- Equivalently, either `a[i] = 0` or `b[i] = 0` (by the negation of intersection, i.e., De Morgan’s law).
	- Hence, `(a[i] AND b[i]) = 0`, matching `c[i]`.

Since these cases cover all indices `i`, the characteristic vector of `A ∩ B` is exactly `a & b`.
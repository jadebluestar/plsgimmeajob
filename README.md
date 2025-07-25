A complete reference for **bitwise operations**, **truth table logic**, and **common LeetCode patterns**.  
Use this to solve bit manipulation problems quickly and efficiently.

---

## 1. **Operators & Truth Tables**

| Operator     | Symbol | Description        | Truth Table (bits)                              |
|-------------|--------|--------------------|------------------------------------------------|
| AND         | `&`    | 1 if both are 1   | 0&0=0, 0&1=0, 1&0=0, 1&1=1                   |
| OR          | `\|`   | 1 if any is 1     | 0\|0=0, 0\|1=1, 1\|0=1, 1\|1=1               |
| XOR         | `^`    | 1 if bits differ  | 0^0=0, 0^1=1, 1^0=1, 1^1=0                   |
| NOT         | `~`    | Flip all bits     | ~1 → 0, ~0 → 1                                |
| LEFT SHIFT  | `<<`   | Shift left (×2)   | `x << 1` → x × 2                              |
| RIGHT SHIFT | `>>`   | Shift right (÷2)  | `x >> 1` → x // 2                             |

---

## 2. **Bitwise Tricks & Common Patterns**

| Trick                       | Code Example                              | Usage                                  |
|----------------------------|------------------------------------------|----------------------------------------|
| Check even/odd            | `n & 1`                                 | 0 → even, 1 → odd                     |
| Check power of 2          | `n > 0 and (n & (n-1)) == 0`           | LC 231                                |
| Remove lowest set bit     | `n &= (n-1)`                            | LC 191 (Hamming Weight)               |
| Get lowest set bit        | `n & -n`                                | Used in LC 260                        |
| Flip ith bit              | `x ^ (1 << i)`                          | Toggle a bit                          |
| Set ith bit               | `x | (1 << i)`                          | Turn a bit ON                         |
| Clear ith bit             | `x & ~(1 << i)`                         | Turn a bit OFF                        |
| Generate all subsets      | `for mask in range(1 << n)`             | LC 78, LC 90                          |

---

## 3. **LeetCode Problems by Category**

### XOR Based
- [136. Single Number](https://leetcode.com/problems/single-number/)
- [137. Single Number II](https://leetcode.com/problems/single-number-ii/)
- [260. Single Number III](https://leetcode.com/problems/single-number-iii/)
- [268. Missing Number](https://leetcode.com/problems/missing-number/)
- [421. Maximum XOR of Two Numbers](https://leetcode.com/problems/maximum-xor-of-two-numbers-in-an-array/)

---

### Bit Counting & Power of Two
- [191. Number of 1 Bits](https://leetcode.com/problems/number-of-1-bits/)
- [231. Power of Two](https://leetcode.com/problems/power-of-two/)
- [342. Power of Four](https://leetcode.com/problems/power-of-four/)
- [338. Counting Bits](https://leetcode.com/problems/counting-bits/)

---

### Subsets & Bitmasking
- [78. Subsets](https://leetcode.com/problems/subsets/)
- [90. Subsets II](https://leetcode.com/problems/subsets-ii/)
- [401. Binary Watch](https://leetcode.com/problems/binary-watch/)

---

### ✅ Advanced Bit Manipulation
- [201. Bitwise AND of Numbers Range](https://leetcode.com/problems/bitwise-and-of-numbers-range/)
- [190. Reverse Bits](https://leetcode.com/problems/reverse-bits/)
- [268. Missing Number](https://leetcode.com/problems/missing-number/)

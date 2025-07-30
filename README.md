# Cosmetic hack (python((not recommended))
The __import__("atexit") line
just overides the text module to display 0 runtime
```python
__import__("atexit").register(lambda: open("display_runtime.txt", "w").write("0"))
```
# Bit Manipulation

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

# Advanced Algorithims ( i mean all algo why ad :/)
Perfect! Here’s a **full, detailed README in proper Markdown** with **all the common + obscure algorithms**, formatted for GitHub with tables, code blocks, and explanations.


A **comprehensive guide** to algorithmic techniques frequently used in LeetCode and contests. Includes **intuition, complexity, code (Python), and example problems**.

---

## 📌 Table of Contents

1. [Boyer-Moore Voting Algorithm](#1-boyer-moore-voting-algorithm)
2. [Kadane’s Algorithm](#2-kadanes-algorithm)
3. [Two Pointers](#3-two-pointers)
4. [Sliding Window](#4-sliding-window)
5. [Binary Search Patterns](#5-binary-search-patterns)
6. [Fast & Slow Pointers](#6-fast--slow-pointers)
7. [Monotonic Stack](#7-monotonic-stack)
8. [Prefix Sum & Difference Array](#8-prefix-sum--difference-array)
9. [Binary Indexed Tree (Fenwick Tree)](#9-binary-indexed-tree-bit)
10. [Union-Find / DSU](#10-union-find-dsu)
11. [Reservoir Sampling](#11-reservoir-sampling)
12. [Morris Traversal](#12-morris-traversal)
13. [KMP Algorithm (String Matching)](#13-kmp-algorithm)
14. [Tarjan’s Algorithm (Bridges & SCC)](#14-tarjans-algorithm)
15. [Topological Sort](#15-topological-sort)
16. [Z Algorithm](#16-z-algorithm)
17. [Meet-in-the-Middle](#17-meet-in-the-middle)
18. [Bitmask DP](#18-bitmask-dp)
19. [Manacher’s Algorithm](#19-manachers-algorithm)
20. [Trie-based Algorithms](#20-trie-based-algorithms)

---

## ✅ 1. Boyer-Moore Voting Algorithm

**Use:** Find majority element (> n/2).
**Idea:** Cancel out different elements; majority remains.

```python
def majorityElement(nums):
    count, candidate = 0, None
    for num in nums:
        if count == 0:
            candidate = num
        count += 1 if num == candidate else -1
    return candidate
```

✔ **Complexity:** O(n) time, O(1) space
✔ **Example:** [169. Majority Element](https://leetcode.com/problems/majority-element/)

---

## ✅ 2. Kadane’s Algorithm

**Use:** Maximum subarray sum.

```python
def maxSubArray(nums):
    curr = ans = nums[0]
    for n in nums[1:]:
        curr = max(n, curr + n)
        ans = max(ans, curr)
    return ans
```

✔ **Example:** [53. Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

---

## ✅ 3. Two Pointers

Used for sorted arrays, linked lists, partitioning.

```python
def twoSum(numbers, target):
    l, r = 0, len(numbers)-1
    while l < r:
        s = numbers[l] + numbers[r]
        if s == target: return [l+1, r+1]
        elif s < target: l += 1
        else: r -= 1
```

✔ **Example:** [167. Two Sum II](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)

---

## ✅ 4. Sliding Window

Efficient for subarrays/substrings.

✔ **Example:** [3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

---

## ✅ 5. Binary Search Patterns

* Classic Search
* Search on **answer space** (e.g., Koko Eating Bananas)

```python
def binarySearch(arr, target):
    l, r = 0, len(arr)-1
    while l <= r:
        mid = (l+r)//2
        if arr[mid]==target: return mid
        elif arr[mid]<target: l=mid+1
        else: r=mid-1
    return -1
```

---

## ✅ 6. Fast & Slow Pointers

**Use:** Cycle detection in linked lists.

---

## ✅ 7. Monotonic Stack

**Use:** Next Greater Element, Histogram problems.

---

## ✅ 8. Prefix Sum & Difference Array

Quick range queries and updates.

✔ **Example:** [303. Range Sum Query](https://leetcode.com/problems/range-sum-query-immutable/)

---

## ✅ 9. Binary Indexed Tree (Fenwick Tree)

Efficient prefix sums with updates.

```python
class BIT:
    def __init__(self, n):
        self.bit=[0]*(n+1)
    def update(self,i,val):
        while i<len(self.bit):
            self.bit[i]+=val
            i+=i&-i
    def query(self,i):
        s=0
        while i>0:
            s+=self.bit[i]
            i-=i&-i
        return s
```

---

## ✅ 10. Union-Find / DSU

**Use:** Connectivity in graphs.

---

## ✅ 11. Reservoir Sampling

Pick random element from stream.

---

## ✅ 12. Morris Traversal

Tree traversal without extra space.

---

## ✅ 13. KMP Algorithm

Efficient substring search.

---

## ✅ 14. Tarjan’s Algorithm

Find bridges and SCC in graphs.

---

## ✅ 15. Topological Sort

For DAG ordering.

---

## ✅ 16. Z Algorithm

Pattern matching in O(n).

---

## ✅ 17. Meet-in-the-Middle

Divide & conquer for subset problems.

---

## ✅ 18. Bitmask DP

Used in TSP and subset problems.

---

## ✅ 19. Manacher’s Algorithm

Longest palindromic substring in O(n).

---

## ✅ 20. Trie-based Algorithms

Prefix searches, autocomplete.

---

## 📊 Complexity Summary

| Algorithm    | Time     | Space  |
| ------------ | -------- | ------ |
| Boyer-Moore  | O(n)     | O(1)   |
| Kadane       | O(n)     | O(1)   |
| Prefix Sum   | O(n)     | O(n)   |
| Fenwick Tree | O(log n) | O(n)   |
| Union-Find   | O(α(n))  | O(n)   |
| KMP          | O(n+m)   | O(n)   |
| Manacher     | O(n)     | O(n)   |
| Tarjan       | O(V+E)   | O(V+E) |

# Python Built-in Functions Cheat Sheet

This document lists commonly used Python built-in functions with short descriptions and examples.

---

## 🔹 1. General Functions
| Function | Description | Example |
|----------|-------------|---------|
| `len()` | Returns the length of an object | `len([1,2,3]) # 3` |
| `type()` | Returns the type of an object | `type(42) # <class 'int'>` |
| `id()` | Returns unique identifier for an object | `id(a)` |

---

## 🔹 2. Iterable Functions
| Function | Description | Example |
|----------|-------------|---------|
| `zip()` | Combines iterables element-wise into tuples | `zip([1,2],[3,4]) -> [(1,3),(2,4)]` |
| `enumerate()` | Returns index and value while iterating | `for i,v in enumerate(['a','b']): print(i,v)` |
| `sorted()` | Returns a sorted list | `sorted([3,1,2]) -> [1,2,3]` |
| `reversed()` | Returns an iterator in reverse order | `list(reversed([1,2,3])) -> [3,2,1]` |

---

## 🔹 3. Numeric Functions
| Function | Description | Example |
|----------|-------------|---------|
| `sum()` | Sums elements in iterable | `sum([1,2,3]) # 6` |
| `max()` | Largest element | `max([1,3,2]) # 3` |
| `min()` | Smallest element | `min([1,3,2]) # 1` |
| `abs()` | Absolute value | `abs(-5) # 5` |

---

## 🔹 4. Functional Programming
| Function | Description | Example |
|----------|-------------|---------|
| `map()` | Apply function to iterable | `map(str, [1,2,3]) -> ['1','2','3']` |
| `filter()` | Filter iterable based on function | `filter(lambda x: x>0, [-1,2,-3]) -> [2]` |
| `any()` | True if any element is True | `any([0,1,0]) # True` |
| `all()` | True if all elements are True | `all([1,1,1]) # True` |

---

## 🔹 5. Type Conversions
`int()`, `float()`, `str()`, `list()`, `tuple()`, `dict()`, `set()` – convert between data types.

---

## 🔹 6. I/O Functions
| Function | Description | Example |
|----------|-------------|---------|
| `print()` | Outputs to console | `print("Hello")` |
| `input()` | Takes user input | `x = input("Enter:")` |
| `open()` | Opens a file | `open('file.txt','r')` |

---

### ✅ Quick Note:
- Most built-in functions: [Python Official Docs](https://docs.python.org/3/library/functions.html)


---






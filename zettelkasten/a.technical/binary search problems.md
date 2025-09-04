---
tags:
  - problem-solving
---

### Common Patterns
### **Pattern 1: Boundary Finding or Counting Occurrences 
**What it finds:** The first/last position where some condition changes from false to true (or vice versa)
**When to use:** Array has a clear "split point" where everything on one side satisfies a condition and everything on the other side doesn't
example problems: 
- [missing numbers](<- https://leetcode.com/problems/missing-number/>)
- [duplicate numbers](https://leetcode.com/problems/find-the-duplicate-number/)

### **Pattern 1.1: Peak/Valley Finding**

**What it finds:** Local maximum/minimum where comparison with neighbors determines search direction

**When to use:**

- Looking for peaks, valleys, or local extrema
- Can compare current position with neighbors to decide direction
- No global sorting, but local comparisons guide the search

- https://leetcode.com/problems/find-peak-element
- https://leetcode.com/problems/peak-index-in-a-mountain-array/


### **Pattern 2: Binary Search on Answer Space** or One-Sided Binary Search

**What it finds:** The optimal value from a range of possible answers by testing if each candidate works

**When to use:** 

- Problem asks for "minimum X such that..." or "maximum X such that..."
- You can write a function to check if a candidate answer is valid
- The validity follows a monotonic pattern (if X works, then X+1 also works, or vice versa)

### **Pattern 3: Binary Search on Answer Space** or One-Sided Binary Search

**What it finds:** The optimal value from a range of possible answers by testing if each candidate works

**When to use:** 

- Problem asks for "minimum X such that..." or "maximum X such that..."
- You can write a function to check if a candidate answer is valid
- The validity follows a monotonic pattern (if X works, then X+1 also works, or vice versa)

### **Pattern 4: sqr root and other roots
The square root of n is the number r such that r2 = n. Square root computations are performed inside every pocket calculator, but it is instructive to develop an efficient algorithm to compute them. First, observe that the square root of n ≥ 1 must be at least 1 and at most n. Let l = 1 and r = n. Consider the midpoint of this interval, m = (l + r)/2. How does m2 compare to n? If n ≥ m2, then the square root must be greater than m, so the algorithm repeats with

problem solved so far from leetcode 
- https://leetcode.com/problems/search-in-rotated-sorted-array/?envType=problem-list-v2
- https://leetcode.com/problems/peak-index-in-a-mountain-array/
- https://leetcode.com/problems/find-peak-element/
- https://leetcode.com/problems/missing-number/
- https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/
- https://leetcode.com/problems/find-the-duplicate-number/
- https://leetcode.com/problems/binary-search/
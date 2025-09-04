---
tags:
  - dp-deck
  - cards
parent: "[[linear dp]]"
type: permanent
---

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security systems connected and **it will automatically contact the police if two adjacent houses were broken into on the same night**. Given an integer array `nums` representing the amount of money of each house, return _the maximum amount of money you can rob tonight ****without alerting the police**_.   **Example 1:**

```
Input: nums = [1,2,3,1]
Output: 4
Explanation: Rob house 1 (money = 1) and then rob house 3 (money = 3).
Total amount you can rob = 1 + 3 = 4.
```

?
```
ALGORITHM CircularHouseRobber
INPUT: nums (array of house values)
OUTPUT: maximum money that can be robbed

1. IF length of nums = 1 THEN
   2. RETURN nums[0]
3. END IF

4. IF length of nums = 2 THEN
   5. RETURN MAXIMUM(nums[0], nums[1])
6. END IF

7. SET n = length of nums

8. FUNCTION RobRange(start, length)
   9. IF length = 1 THEN
      10. RETURN nums[start MOD n]
   10. END IF
   11. IF length = 2 THEN
      13. RETURN MAXIMUM(nums[start MOD n], nums[(start + 1) MOD n])
   12. END IF
   13. SET prev2 = nums[start MOD n]
   14. SET prev1 = MAXIMUM(nums[start MOD n], nums[(start + 1) MOD n])
   15. FOR i = 2 TO length - 1 DO
      18. SET currentIdx = (start + i) MOD n
      19. SET current = MAXIMUM(prev1, nums[currentIdx] + prev2)
      20. SET prev2 = prev1
      21. SET prev1 = current
   16. END FOR
   17. RETURN prev1
18. END FUNCTION

19. SET scenario1 = RobRange(0, n - 1)     // Exclude last house
20. SET scenario2 = RobRange(1, n - 1)     // Exclude first house

21. RETURN MAXIMUM(scenario1, scenario2)
```
**RobRange Function:**
- Solves the linear house robber problem for a given range
- Uses modulo (`MOD n`) to handle circular array indexing
- Space-optimized: only tracks previous two values instead of full DP table
**Main Logic:**
- Handle edge cases for arrays of length 1 or 2
- Split the circular problem into two linear subproblems
- Use modulo arithmetic to handle circular indexing
**Two Scenarios:**
- **Scenario 1**: Consider houses 0 to n-2 (can rob first house, cannot rob last)
- **Scenario 2**: Consider houses 1 to n-1 (can rob last house, cannot rob first)
<!--SR:!2025-07-03,1,230--> 
++

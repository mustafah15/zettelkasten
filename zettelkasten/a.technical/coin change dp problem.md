---
tags:
  - "#dp-deck"
  - "#cards"
related: "[[linear dp]]"
type: permanent
---
You are given an integer array `coins` representing coins of different denominations and an integer `amount` representing a total amount of money.
Return _the fewest number of coins that you need to make up that amount_. If that amount of money cannot be made up by any combination of the coins, return `-1`.
You may assume that you have an infinite number of each kind of coin.
**Example 1:**
**Input:** coins = [1,2,5], amount = 11
**Output:** 3
**Explanation:** 11 = 5 + 5 + 1
?
- Initialize an array where `dp[i]` represents the minimum coins needed for amount `i` and set all elements to INFINITY
- Base case: 0 coins needed for amount 0
- For each amount from 1 to target, try using each available coin denomination
- Update the minimum coins needed by considering adding one more coin to a previously computed subproblem
- Return the result for the target amount, or -1 if no solution exists
<!--SR:!2025-07-03,1,230-->

++


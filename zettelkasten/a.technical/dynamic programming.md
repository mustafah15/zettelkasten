---
tags:
  - problem-solving
  - software-engineering
type: permanent
deeper: "[[dp common patterns and problems]]"
---
## summary 

in this document I'm trying to explain how to solve dynamic programming leetcode problems with common patterns and techniques 


### what is dynamic programming in the first place?

in simple words it's recursion + memoization 


### steps to solve the problem

1. identify sub problem structure  
	1. break down the problem into smaller, overlapping subproblems
	2. ask " what's the smallest version of this problem I can solve?"
	3. look for recursive relationships between current state and previous states
2. define state variables 
	1. determine what parameters uniquely define each subproblem
	2. common state variables usually are: position/index, remaining capacity, current sum, etc.
	3. for 2d problems: often `dp[i][j]` where i and j represent different dimensions 
3. establish base cases
	1. identify the simplest case that can be solved directly 
	2. these form the foundation for building up larger problems
	3. often involves empty array single element or boundary condition
4. find the recurrence relation 
	1. express current state in terms of previous states
	2. this is the heart of the db solution
5. choose implementation approach 
	1. **top-down(memoization)** : start with recursive solution add caching 
	2. bottom-up(tabulation) : build solution iteratively from the base cases tabulation often more space-efficient and avoids recursion stack limits


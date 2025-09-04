---
tags:
  - problem-solving
  - dynamic-programming
related: "[[dynamic programming]]"
type: permanent
---


### [[linear dp]]
#### **Grid DP**
2D problems, often path-finding or matrix traversal
examples are
- **Unique Paths (LeetCode 62)**
	- `dp[i][j] = dp[i-1][j] + dp[i][j-1]`
	- Paths from top-left to bottom-right
- **Minimum Path Sum (LeetCode 64)
	- **`dp[i][j] = grid[i][j] + min(dp[i-1][j], dp[i][j-1])`
	- Cheapest path through grid
- **Longest Common Subsequence (LeetCode 1143)**
	- `dp[i][j] = dp[i-1][j-1] + 1` if match, else `max(dp[i-1][j], dp[i][j-1])`
	- 2D representation of two strings
- **Edit Distance (LeetCode 72)**
	- Three operations: insert, delete, replace
	- `dp[i][j]` = min edit distance between substrings

- more examples and 
#### **Interval DP**
Problems on ranges/subarrays, often with nested loops
examples problems are:
- **Longest Palindromic Substring (LeetCode 5)**
	- `dp[i][j]` = true if substring from i to j is palindrome
	- Build from smaller intervals to larger
- **Burst Balloons (LeetCode 312)**
	- `dp[i][j]` = maximum coins from bursting balloons between i and j
	- Consider which balloon to burst last
- **Palindrome Partitioning II (LeetCode 132)**
	- Minimum cuts to partition string into palindromes
	- Combine interval checking with linear DP


#### **Tree DP**
Problems on tree structures often DFS with memoization
- **House Robber III (LeetCode 337)**
	- For each node: max money if rob vs don't rob
	- `dfs(node)` returns `[rob_node, dont_rob_node]`

- **Binary Tree Maximum Path Sum (LeetCode 124)**
	- For each node: consider path through node vs path ending at node
	- Global maximum tracking

- **Diameter of Binary Tree (LeetCode 543)**
	- For each node: longest path through this node
	- Combine left and right subtree depths
- **Tree Distance Sum**
	- Sum of distances from each node to all other nodes
	- Root and re-root technique

#### **Bitmask DP**
When state involves subsets, use bits to represent which elements are used

examples problems are:
**Traveling Salesman Problem (TSP)**
- `dp[mask][i]` = minimum cost to visit cities in mask, ending at city i
- Each bit represents whether city is visited

**Subset Sum with Bitmask**
- `dp[mask]` = true if subset represented by mask has target sum
- Each bit represents whether element is included

**Maximum Students Taking Exam (LeetCode 1349)**
- `dp[row][mask]` = maximum students in first row rows, with mask representing current row seating
- Validate seating arrangements

**Shortest Path Visiting All Nodes (LeetCode 847)**
- `dp[mask][node]` = shortest path visiting all nodes in mask, ending at node
- BFS with bitmask state


Each pattern has its own state representation and transition logic, but they all follow the core DP principles of optimal substructure and overlapping subproblems.

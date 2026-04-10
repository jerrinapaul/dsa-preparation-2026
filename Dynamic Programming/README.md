# 📚 DSA Preparation – Dynamic Programming (Top 20)

Track your progress on **Dynamic Programming (DP)** problems.
Update `[ ] → [x]` when completed.

---

## 🚀 Problem Tracker

| Done | #  | Problem                        | Difficulty | Pattern            | Link                                                          | Basic Idea                            |
| ---- | -- | ------------------------------ | ---------- | ------------------ | ------------------------------------------------------------- | ------------------------------------- |
| [ ]  | 1  | Climbing Stairs                | Easy       | 1D DP              | https://leetcode.com/problems/climbing-stairs/                | `dp[i] = dp[i-1] + dp[i-2]`           |
| [ ]  | 2  | House Robber                   | Medium     | 1D DP              | https://leetcode.com/problems/house-robber/                   | Choose max of rob or skip             |
| [ ]  | 3  | House Robber II                | Medium     | Circular DP        | https://leetcode.com/problems/house-robber-ii/                | Solve two ranges (exclude first/last) |
| [ ]  | 4  | Coin Change                    | Medium     | Unbounded Knapsack | https://leetcode.com/problems/coin-change/                    | Min coins using DP array              |
| [ ]  | 5  | Coin Change II                 | Medium     | Combinations DP    | https://leetcode.com/problems/coin-change-ii/                 | Count ways using DP                   |
| [ ]  | 6  | Longest Increasing Subsequence | Medium     | DP + Binary Search | https://leetcode.com/problems/longest-increasing-subsequence/ | Track increasing subsequence          |
| [ ]  | 7  | Longest Common Subsequence     | Medium     | 2D DP              | https://leetcode.com/problems/longest-common-subsequence/     | Match chars or take max of neighbors  |
| [ ]  | 8  | Edit Distance                  | Hard       | 2D DP              | https://leetcode.com/problems/edit-distance/                  | Insert/delete/replace operations      |
| [ ]  | 9  | Unique Paths                   | Medium     | Grid DP            | https://leetcode.com/problems/unique-paths/                   | `dp[i][j] = top + left`               |
| [ ]  | 10 | Unique Paths II                | Medium     | Grid DP            | https://leetcode.com/problems/unique-paths-ii/                | Same as above with obstacles          |
| [ ]  | 11 | Minimum Path Sum               | Medium     | Grid DP            | https://leetcode.com/problems/minimum-path-sum/               | Choose min from top/left              |
| [ ]  | 12 | Triangle                       | Medium     | Bottom-up DP       | https://leetcode.com/problems/triangle/                       | Build from bottom row                 |
| [ ]  | 13 | Partition Equal Subset Sum     | Medium     | 0/1 Knapsack       | https://leetcode.com/problems/partition-equal-subset-sum/     | Subset sum equals target              |
| [ ]  | 14 | Target Sum                     | Medium     | DP + Subset        | https://leetcode.com/problems/target-sum/                     | Convert to subset sum                 |
| [ ]  | 15 | Maximum Product Subarray       | Medium     | DP                 | https://leetcode.com/problems/maximum-product-subarray/       | Track max & min product               |
| [ ]  | 16 | Decode Ways                    | Medium     | 1D DP              | https://leetcode.com/problems/decode-ways/                    | Count valid decodings                 |
| [ ]  | 17 | Word Break                     | Medium     | DP + HashSet       | https://leetcode.com/problems/word-break/                     | Check valid splits using dictionary   |
| [ ]  | 18 | Palindromic Substrings         | Medium     | Expand / DP        | https://leetcode.com/problems/palindromic-substrings/         | Expand around center                  |
| [ ]  | 19 | Longest Palindromic Substring  | Medium     | DP / Expand        | https://leetcode.com/problems/longest-palindromic-substring/  | Track longest palindrome              |
| [ ]  | 20 | Burst Balloons                 | Hard       | Interval DP        | https://leetcode.com/problems/burst-balloons/                 | Try last balloon to burst             |

---

## 🧠 DP Thinking Template

```csharp
// 1. Define DP state
// dp[i] = answer for subproblem

// 2. Recurrence relation
dp[i] = Math.Max(dp[i-1], dp[i-2] + nums[i]);

// 3. Base case
dp[0] = nums[0];
```

---

## 📊 Progress

Completed: **0 / 20**

---

## 🎯 Goal

Master:

* 1D DP
* 2D DP
* Knapsack patterns
* Grid problems
* Interval DP

---

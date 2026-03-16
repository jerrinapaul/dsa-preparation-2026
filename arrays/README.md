# Arrays Problems

This repository contains solutions and notes for important array problems frequently asked in coding interviews.

## 🚀 Problem List
---

| done | # | Question | Pattern | Link | Basic Solution Idea |
|---|---|---|---|---|---|
| - [x]  | 1 | Two Sum | HashMap | https://leetcode.com/problems/two-sum/ | Store number → index in dictionary. For each number check `target - num`. |
| - [x]  | 2 | Best Time to Buy and Sell Stock | Greedy | https://leetcode.com/problems/best-time-to-buy-and-sell-stock/ | Track minimum price so far and update max profit. |
| - [x]  | 3 | Maximum Subarray | Kadane's Algorithm | https://leetcode.com/problems/maximum-subarray/ | Keep running sum. Reset if sum becomes negative. |
| - [x]  | 4 | Maximum Product Subarray | Dynamic Tracking | https://leetcode.com/problems/maximum-product-subarray/ | Track both `maxProduct` and `minProduct` because negatives flip sign. |
| [ ]  | 5 | Product of Array Except Self | Prefix + Suffix | https://leetcode.com/problems/product-of-array-except-self/ | Compute prefix product and suffix product separately. |
| [ ]  | 6 | Move Zeroes | Two Pointers | https://leetcode.com/problems/move-zeroes/ | Move non-zero elements forward and fill remaining with zero. |
| [ ]  | 7 | Container With Most Water | Two Pointers | https://leetcode.com/problems/container-with-most-water/ | Start both ends, move smaller height pointer inward. |
| [ ]  | 8 | 3Sum | Sorting + Two Pointers | https://leetcode.com/problems/3sum/ | Sort array, fix one number, use two-pointer to find remaining pair. |
| [ ]  | 9 | Find the Duplicate Number | Cycle Detection | https://leetcode.com/problems/find-the-duplicate-number/ | Use Floyd’s slow/fast pointer to detect cycle. |
| [ ]  | 10 | Minimum Size Subarray Sum | Sliding Window | https://leetcode.com/problems/minimum-size-subarray-sum/ | Expand window until sum ≥ target then shrink from left. |
| [ ]  | 11 | Subarray Sum Equals K | Prefix Sum + HashMap | https://leetcode.com/problems/subarray-sum-equals-k/ | Track cumulative sum. If `sum - k` exists in map, add count. |
| [ ]  | 12 | Merge Intervals | Sorting + Greedy | https://leetcode.com/problems/merge-intervals/ | Sort intervals by start, merge overlapping intervals. |
| [ ]  | 13 | Insert Interval | Interval Manipulation | https://leetcode.com/problems/insert-interval/ | Add intervals before new interval, merge overlapping ones. |
| [ ]  | 14 | Search in Rotated Sorted Array | Binary Search | https://leetcode.com/problems/search-in-rotated-sorted-array/ | Determine which half is sorted and search accordingly. |
| [ ]  | 15 | Find Minimum in Rotated Sorted Array | Binary Search | https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/ | Compare mid with right pointer to find pivot. |
| [ ]  | 16 | Set Matrix Zeroes | Matrix Marking | https://leetcode.com/problems/set-matrix-zeroes/ | Use first row/column as markers to avoid extra space. |
| [ ]  | 17 | Spiral Matrix | Matrix Traversal | https://leetcode.com/problems/spiral-matrix/ | Maintain four boundaries and traverse layer by layer. |
| [ ]  | 18 | Trapping Rain Water | Two Pointers | https://leetcode.com/problems/trapping-rain-water/ | Track leftMax and rightMax while moving pointers. |
| [ ]  | 19 | Sliding Window Maximum | Monotonic Deque | https://leetcode.com/problems/sliding-window-maximum/ | Maintain deque of decreasing elements for max window value. |
| [ ]  | 20 | Next Permutation | Array Manipulation | https://leetcode.com/problems/next-permutation/ | Find first decreasing element, swap with next greater, reverse suffix. |

---

## 🧠 Patterns Covered

- HashMap
- Greedy
- Kadane's Algorithm
- Prefix Sum
- Two Pointers
- Sliding Window
- Binary Search
- Interval Problems
- Matrix Traversal
- Monotonic Queue

---

## 🎯 Goal

Mastering these 20 problems builds a strong foundation in:

- Array manipulation
- Problem-solving patterns
- Coding interview preparation


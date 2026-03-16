# Arrays Problems

This repository contains solutions and notes for important array problems frequently asked in coding interviews.

## 🚀 Problem List
# 📚 DSA Preparation – Sliding Window Problems

Track progress for **Sliding Window pattern problems**.
Tick the checkbox (`[ ] → [x]`) once the problem is completed.

---

## 🚀 Problem Tracker

| Done | #  | Problem                                               | Difficulty | Pattern                          | Link                                                                                   | Basic Idea                                                   |
| ---- | -- | ----------------------------------------------------- | ---------- | -------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| [ ]  | 1  | Maximum Average Subarray I                            | Easy       | Fixed Sliding Window             | https://leetcode.com/problems/maximum-average-subarray-i/                              | Maintain window sum of size `k` and update max average       |
| [ ]  | 2  | Minimum Size Subarray Sum                             | Medium     | Dynamic Sliding Window           | https://leetcode.com/problems/minimum-size-subarray-sum/                               | Expand window until sum ≥ target then shrink                 |
| [ ]  | 3  | Longest Substring Without Repeating Characters        | Medium     | Sliding Window + HashSet         | https://leetcode.com/problems/longest-substring-without-repeating-characters/          | Maintain set of characters and shrink when duplicate appears |
| [ ]  | 4  | Find All Anagrams in a String                         | Medium     | Fixed Window + Frequency Map     | https://leetcode.com/problems/find-all-anagrams-in-a-string/                           | Compare character frequency of window with target string     |
| [ ]  | 5  | Permutation in String                                 | Medium     | Sliding Window + Frequency Count | https://leetcode.com/problems/permutation-in-string/                                   | Check if any window matches frequency of `s1`                |
| [ ]  | 6  | Longest Repeating Character Replacement               | Medium     | Sliding Window + Max Frequency   | https://leetcode.com/problems/longest-repeating-character-replacement/                 | Allow replacement if window size − maxCharCount ≤ k          |
| [ ]  | 7  | Fruit Into Baskets                                    | Medium     | At Most K Distinct               | https://leetcode.com/problems/fruit-into-baskets/                                      | Sliding window with at most 2 distinct values                |
| [ ]  | 8  | Maximum Number of Vowels in Substring of Given Length | Medium     | Fixed Sliding Window             | https://leetcode.com/problems/maximum-number-of-vowels-in-a-substring-of-given-length/ | Maintain vowel count in window of size `k`                   |
| [ ]  | 9  | Maximum Erasure Value                                 | Medium     | Sliding Window + HashSet         | https://leetcode.com/problems/maximum-erasure-value/                                   | Maintain unique elements and track sum                       |
| [ ]  | 10 | Sliding Window Maximum                                | Hard       | Monotonic Deque                  | https://leetcode.com/problems/sliding-window-maximum/                                  | Use deque to maintain decreasing values                      |
| [ ]  | 11 | Longest Subarray of 1's After Deleting One Element    | Medium     | Sliding Window                   | https://leetcode.com/problems/longest-subarray-of-1s-after-deleting-one-element/       | Maintain at most one zero in window                          |
| [ ]  | 12 | Grumpy Bookstore Owner                                | Medium     | Sliding Window                   | https://leetcode.com/problems/grumpy-bookstore-owner/                                  | Use window to maximize extra satisfied customers             |
| [ ]  | 13 | Maximum Erasure Value                                 | Medium     | Unique Sliding Window            | https://leetcode.com/problems/maximum-erasure-value/                                   | Expand window with unique elements and track sum             |
| [ ]  | 14 | Binary Subarrays With Sum                             | Medium     | Prefix Sum + Sliding Window      | https://leetcode.com/problems/binary-subarrays-with-sum/                               | Count subarrays with exact sum using prefix counts           |
| [ ]  | 15 | Diet Plan Performance                                 | Easy       | Fixed Window                     | https://leetcode.com/problems/diet-plan-performance/                                   | Maintain window sum and compare with thresholds              |

---

## 📊 Progress

Completed: **0 / 15**

To mark complete:

```
[ ] → [x]
```

Example:

```
[x] Minimum Size Subarray Sum
```

---

## 🧠 Sliding Window Template (C#)

```csharp
int left = 0;

for (int right = 0; right < nums.Length; right++)
{
    // expand window logic

    while (windowInvalid)
    {
        // shrink window
        left++;
    }

    // update result
}
```

---


| # | Question | Pattern | Link | Basic Solution Idea |
|---|---|---|---|---|
| - [ ] | 1 | Two Sum | HashMap | https://leetcode.com/problems/two-sum/ | Store number → index in dictionary. For each number check `target - num`. |
| [x ]  | 2 | Best Time to Buy and Sell Stock | Greedy | https://leetcode.com/problems/best-time-to-buy-and-sell-stock/ | Track minimum price so far and update max profit. |
| [ ]  | 3 | Maximum Subarray | Kadane's Algorithm | https://leetcode.com/problems/maximum-subarray/ | Keep running sum. Reset if sum becomes negative. |
| [ ]  | 4 | Maximum Product Subarray | Dynamic Tracking | https://leetcode.com/problems/maximum-product-subarray/ | Track both `maxProduct` and `minProduct` because negatives flip sign. |
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


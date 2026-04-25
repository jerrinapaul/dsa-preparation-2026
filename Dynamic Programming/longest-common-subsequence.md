# Longest-common-Subsequence

## https://leetcode.com/problems/longest-common-subsequence
Paste link here

## Difficulty
Easy / Medium / Hard

## Pattern
(Hash Map / Two Pointer / Sliding Window / Prefix Sum / etc)

---

## Brute Force Approach

### Idea
Explain briefly

### Time Complexity
O()

### Space Complexity
O()

---
## Final C# Code

```csharp
public class Solution {
    private string t1, t2;
    private Dictionary<(int, int), int> cache = new Dictionary<(int, int), int>();
    private int solve(int i, int j) {
        if (i >= t1.Length || j >= t2.Length) {
            return 0;
        }
        if (cache.ContainsKey((i, j))) {
            return cache[(i, j)];
        }

        int ans;
        if (t1[i] == t2[j]) {
            ans = 1 + solve(i + 1, j + 1);
        } else {
            ans = Math.Max(solve(i + 1, j), solve(i, j + 1));
        }
        cache[(i, j)] = ans;
        return ans;
    }

    public int LongestCommonSubsequence(string text1, string text2) {
        this.t1 = text1;
        this.t2 = text2;
        return solve(0, 0);
    }
}
```

## Optimized Approach

### Idea
Explain briefly

### Time Complexity
O()

### Space Complexity
O()

---

## Key Insight
What made the optimized solution work?

---

## Mistakes I Made
- Mistake 1
- Mistake 2

---

## Edge Cases
- Empty array
- Single element
- etc

---

## Final C# Code

```csharp
public class Solution {
    public int LongestCommonSubsequence(string text1, string text2) {
        int m = text1.Length;
        int n = text2.Length;
        int[][] dp = new int[m + 1][];
        for (int i = 0; i < dp.Length; i++) {
            dp[i] = new int[n + 1];
        }

        for (int i = m - 1; i >= 0; i--) {
            for (int j = n - 1; j >= 0; j--) {
                if (text1[i] == text2[j]) {
                    dp[i][j] = 1 + dp[i + 1][j + 1];
                } else {
                    dp[i][j] = Math.Max(dp[i + 1][j], dp[i][j + 1]);
                }
            }
        }

        return dp[0][0];
    }
}

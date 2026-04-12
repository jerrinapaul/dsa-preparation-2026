# Longest Palindromic Substring

##[ Problem Link
Paste link here](https://leetcode.com/problems/longest-palindromic-substring/)

## Medium 

## Pattern
(Dynamic Programming, Two pointer)

---

## Brute Force Approach

### Idea
check all sub string from length 3 to n, base condition when length is 1 and length is 2.

### Time Complexity
O()
---
```csharp
public string LongestPalindrome(string s) {

        int n = s.Length;
        if( n == 0)
        {
            return "";
        }
        
        int start = 0;
        int maxL = 1;

        bool[][] dp = new bool[n+1][];

        for(int i=0;i<n;i++)
        {
            dp[i] = new bool[n+1];
        }

        for(int i=0; i < n ; i++)
        {
            dp[i][i] = true;
        }

        for(int i=0; i<n-1; i++)
        {
            if(s[i] == s[i+1])
            {
                dp[i][i+1] = true;
                maxL = 2;
                start = i;

            }
        }
        
        for(int subL = 3; subL <= n ; subL++)
        {
            for(int i=0; i<= n-subL; i++)
            {
                int j = i + subL-1;
                if(s[i] == s[j] && dp[i+1][j-1] == true)
                {
                    dp[i][j] = true;
                    maxL = subL;
                    start = i;
                }
            }
        }
        return s.Substring(start, maxL);
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

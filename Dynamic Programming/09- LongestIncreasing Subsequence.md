# longest-increasing-subsequence

## https://leetcode.com/problems/longest-increasing-subsequence

##  Medium 

## Pattern
(DP)

---

## Brute Force Approach

### Idea
Explain briefly

### Time Complexity
O(n^2)

### Space Complexity
O(n)

```csharp
public class Solution {
    public int LengthOfLIS(int[] nums) {
        int n = nums.Length;
        int[] lis = new int[n+1];
        int res = int.MinValue;
      
        for(int i= 0; i < n; i ++)
        {
            lis[i] = 1;
        }
        for(int i = n-1; i >= 0; i--){
                for(int j = i+1; j< n; j++){
                    if(nums[i] < nums[j]){                   
                        lis[i] = Math.Max(lis[i], 1+ lis[j]);
                    }
                }
                res = Math.Max(res, lis[i]);
        }
       return res;
    }
}
```
---

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

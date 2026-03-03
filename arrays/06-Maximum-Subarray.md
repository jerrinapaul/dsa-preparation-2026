# Maximum Subarray

## [Problem Link](https://leetcode.com/problems/maximum-subarray/description/)
Paste link here

## Difficulty
Medium

## Pattern
(DP)

## Optimized Approach

### Idea
Kadane's algo 

### Time Complexity
O(n)

### Space Complexity
O(1)

---

## Key Insight
We use Kadane’s Algorithm:
Maintain a running sum (sum) as we iterate through the array.
Add the current element to sum.
Update the maximum sum (maxSum) whenever sum is greater than the current maxSum.
If sum becomes negative, reset it to 0, since continuing with a negative sum would only hurt future subarray sums.
At the end, maxSum will hold the largest sum of any contiguous subarray.

---

## Mistakes I Made
- curSum= first element of array then iterate from 1st index not from 0th index . i tranversed from 0th.
---

## Edge Cases
- Empty array
- Single element
---

## Final C# Code

```csharp
public class Solution {
    public int MaxSubArray(int[] nums) {
        int curSum =nums[0];
        int maxSum = curSum;
        for(int i =1; i< nums.Length; i++)
        {
            curSum = Math.Max(curSum+nums[i],nums[i]);
            maxSum = Math.Max(maxSum,curSum);
        }
        return maxSum;
        
    }
}

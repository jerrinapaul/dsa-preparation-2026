# target-sum

## https://leetcode.com/problems/target-sum/

## Difficulty
 Medium 

## Pattern
(Hash Map / DP)

---


## Optimized Approach

### Idea
the recursive pattern, have to add the next element and substract next element to reach the target value.
solve(idx+1,nums,target-nums[idx]) + solve(idx+1, nums, target+nums[idx]);

### Time Complexity
O()

### Space Complexity
O()

---

## Key Insight
What made the optimized solution work?

---

## Mistakes I Made
- cache key should be both index and target
- Whatever is the input to recursion we keep that as key

---

## Edge Cases
- Empty array
- Single element
- etc

---

## Final C# Code

```csharp
public class Solution {
    public Dictionary<(int,int), int> dict = new Dictionary<(int, int), int>();
    public int solve(int idx, int[] nums, int target){
        if(idx >=nums.Length)
            return target == 0 ? 1: 0;
        if(dict.ContainsKey((idx, target)))
        {
            return dict[(idx, target)];
        }
        dict[(idx, target)] = solve(idx+1,nums,target-nums[idx]) + solve(idx+1, nums, target+nums[idx]);
        return dict[(idx, target)];
    }
    public int FindTargetSumWays(int[] nums, int target) {
        return solve(0,nums,target);
    }
}
```

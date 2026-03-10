# subarray-sum-equals-k

## https://leetcode.com/problems/subarray-sum-equals-k

## Difficulty
Easy / Medium / Hard

## Pattern
(Hash Map /Prefix Sum / etc)

---
## Optimized Approach

### Idea
If ( preSum ) is not in the map, add it with a frequency of 1.

If ( preSum ) is already in the map, increment its frequency.



### Time Complexity
O()

### Space Complexity
O()

---

## Key Insight
What made the optimized solution work? 

---

## Mistakes I Made
- what should i add in the hashmap value; If ( preSum ) is already in the map, increment its frequency.
-  if(map.TryGetValue(cumSum - k, out int value))
-  forget to add ! if (!map.TryAdd(cumSum, 1))

---

## Edge Cases
- Empty array
- Single element
- etc

---

## Final C# Code

```csharp
public class Solution {
    public int SubarraySum(int[] nums, int k) {
        Dictionary<int, int> map = new Dictionary<int,int>(nums.Length);
         map.Add(0,1);
        int cumSum = 0;
        int res = 0;
        for(int i = 0; i < nums.Length; i++)
        {
            cumSum +=nums[i];
            if(map.ContainsKey(cumSum - k))
            {
                res += map[cumSum - k];
            }
            if (!map.TryAdd(cumSum, 1))
            {
                 
                map[cumSum]++;
            }
        }
        return res;
    }
}

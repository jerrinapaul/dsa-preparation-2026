
Status:
Not solved yet

# Two Sum
## https://leetcode.com/problems/two-sum/
Paste link here

## Difficulty
Easy 

## Pattern
(Hash Map)


## Optimized Approach

### Idea
Find the difference and see keep a map with difference and index , if it coming again mean we found the two number which will sum to target and return the index.

### Time Complexity
O(n)

### Space Complexity
O(1)

## Mistakes I Made
- syntax error
- putting th wrong key in the map

## Edge Cases

## Final C# Code

```csharp
public class Solution {
  public int[] TwoSum(int[] nums, int target)
  {
    Dictionary<int, int> seen = new Dictionary<int, int>();
    for(int i=0; i <nums.Length; i++)
    {
      int dif = target - nums[i];
      if(seen.ContainsKey(dif))
      {
        return new int[] {seen[dif], i};
      }
      seen[nums[i]] = i;
    }
    return new int[] {};
  }
}

   

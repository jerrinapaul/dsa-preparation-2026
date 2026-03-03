# Problem Name

## https://leetcode.com/problems/remove-duplicates-from-sorted-array

## Difficulty
Easy 

## Pattern
Two Pointers

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
2 pointers compare and when it is not matching move the number to slow pointer.

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
    public int RemoveDuplicates(int[] nums) {
        int np=0;
        for(int i=0; i<nums.Length; i++)
        {
            if(nums[np] != nums[i])
            {
                np = np+1;
                nums[np]=nums[i];            
            }
        }
        return np+1;
    }
}

# Move Zeroes

## https://leetcode.com/problems/move-zeroes/


## Difficulty
Easy

## Pattern
(Two pointers)

---

## Optimized Approach

### Idea
 Maintain pointer for next non-zero position and swap

### Time Complexity
O(n)
### Space Complexity
O(1)

---


## Mistakes I Made
- Mistake 1
- Mistake 2

---

## Edge Cases

## Final C# Code

```csharp
public class Solution {
    public void MoveZeroes(int[] nums) {
        int j =0;
        for(int i=0; i<nums.Length; i++)
        {
            if(nums[i] != 0)
            {
                nums[j] = nums[i];
                j++;
            }       
        }
        for(int k=j; k<nums.Length; k++)
        {
            nums[k]=0;
        }
    }
    
}

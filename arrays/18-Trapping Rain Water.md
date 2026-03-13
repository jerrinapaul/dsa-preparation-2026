# Trapping Rain Water

## https://leetcode.com/problems/trapping-rain-wate

## Difficulty
Hard

## Pattern
( Two Pointer)

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
public class Solution {
    public int Trap(int[] height) {
        int[] left_h = new int[height.Length];
        int[] right_h = new int[height.Length];
        int ans = 0;
        for(int i = 1; i < height.Length; i++)
        {
            left_h[i] = Math.Max(height[i-1],left_h[i-1]);
        }
        for(int i = height.Length - 2; i >= 0; i--)
        {
            right_h[i] = Math.Max(height[i+1], right_h[i+1]);
        }
        int wh;
        for(int i = 0; i < height.Length; i++)
        {
            wh = Math.Max(Math.Min(left_h[i],right_h[i]) - height[i] , 0);
            ans += wh;
        }
        return ans;
    }
}

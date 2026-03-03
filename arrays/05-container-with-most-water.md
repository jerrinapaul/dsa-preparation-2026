# PContainer With Most Water

## https://leetcode.com/problems/container-with-most-water/

## Difficulty
 Medium

## Pattern
(Two Pointer)

---

## Optimized Approach

### Idea
Use two pointer and move the pointer which has less height 

### Time Complexity
O(n)

### Space Complexity
O(1)

---

## Key Insight
Move the pointer pointing to the smaller height

---

## Mistakes I Made
- just increased and reduced the two pointered without thinking when to move the pointer
- jumping into the conclusion because of stress and feeling i wont be able to do . fear of failure i am not good 

---

## Edge Cases
- maxarea 0
- ## Final C# Code

```csharp
public int MaxArea(int[] height)
{
    int left = 0;
    int right = height.Length - 1;
    int maxArea = 0;

    while (left < right)
    {
        int width = right - left;
        int minHeight = Math.Min(height[left], height[right]);
        int area = width * minHeight;

        maxArea = Math.Max(maxArea, area);

        if (height[left] < height[right])
            left++;
        else
            right--;
    }

    return maxArea
}



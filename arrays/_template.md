# Problem Name

## Problem Link
Paste link here

## Difficulty
Easy / Medium / Hard

## Pattern
(Hash Map / Two Pointer / Sliding Window / Prefix Sum / etc)

---

## Brute Force Approach

### Idea
Explain briefly

### Time Complexity
O()

### Space Complexity
O()

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
    public int[][] Merge(int[][] intervals) {

        if(intervals.Length == 0)
            return new int[0][];
        
        Array.Sort(intervals, (a,b => a[0].CompareTo(b[0])));
        int[] prev = interval[0];
        for(int i = 1; i< intervals.Length; i++)
        {
            int[] interval = interval[i];
            List<int[]> merged = new List<int[]>();
            // start of next is smaller than end of prev merge
            if(interval[0] <= prev[1])
            {
                prev[1] = Math.Max(interval[1], prev[1]);
            }
            else
            {
                merged.Add(prev);
                prev = interval;
            }
        }
        
        merged.Add(prev);
        return merged.ToArray();
    }
}

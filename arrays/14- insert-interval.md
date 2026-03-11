# Insert-interval

## https://leetcode.com/problems/insert-interval/

## Difficulty
 Medium 

## Pattern
(interval manipulation)

---


## Optimized Approach

### Idea
Explain briefly

### Time Complexity
O(n)

### Space Complexity
O(1)

---

## Key Insight
What made the optimized solution work?

---

## Mistakes I Made
- i tried to solve the solution in one while loop so go the error
- tried to write a solution that is coming in your head for more clarity
- Split the method as simple. dont over complicate the logic

---

## Edge Cases
- Empty array
- Single element
- etc

---

## Final C# Code

```csharp
public class Solution {
    public int[][] Insert(int[][] intervals, int[] newInterval) {
        List<int[]> inList = new List<int[]>();
        int i = 0; 
        /*
        1. add all the intervals before new intervals to list
        2. Add the new interval and merge all the interal which are overalaping
        3. add all the non overalaping intervals to list
        */
        while(i < intervals.Length && intervals[i][1] < newInterval[0])
        {
            inList.Add(intervals[i]);
            i++;
        }

        while(i< intervals.Length && intervals[i][0] <= newInterval[1])
        {
            newInterval[0] = Math.Min(intervals[i][0], newInterval[0]);
            newInterval[1] = Math.Max(intervals[i][1], newInterval[1]);
            i++;
        }
        inList.Add(newInterval);

        while(i < intervals.Length)
        {
            inList.Add(intervals[i]);
            i++;
        }

        return inList.ToArray();
      
    }
}

# Contains Duplicate

## https://leetcode.com/problems/contains-duplicate


## Difficulty
Easy

## Pattern
(Hash Set)

---

## Optimized Approach

### Idea
Create a hash set and compare the length of hash set and length of arry if it same no duplicate

### Time Complexity
O(n)

### Space Complexity
O(1)

---

## Key Insight
What made the optimized solution work?

---

## Mistakes I Made
- forget to put > here HashSet<int> set = new HashSet<int>(nums);
- nums.GroupBy(x=>x).Any(x=>x.Count()>1); forget to add () for Count method. in LINQ

---

## Edge Cases
- Empty array
- Single element
- etc

---

## Final C# Code

```csharp

public class Solution {
    public bool ContainsDuplicate(int[] nums) {
       HashSet<int> set = new HashSet<int>(nums);
       return nums.Length != set.Count;
    }
}

public class Solution {
    public bool ContainsDuplicate(int[] nums) {
       return nums.GroupBy(x=>x).Any(x=>x.Count()>1);
    }
}

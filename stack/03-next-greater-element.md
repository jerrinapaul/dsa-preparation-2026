# next-greater-element

## https://leetcode.com/problems/next-greater-element-i

## Difficulty
Easy

## Pattern
(monotonic stack/ Map)

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
O(n)

### Space Complexity
O(n)

---

## Key Insight
- start from end of array to find the max value
- stack should be monotonic decreasing
- 
---

## Mistakes I Made
- Add one extra array for nums2 result, use the map to store the result.
- while condition should be less 

---

## Edge Cases
- Empty array
- Single element
- etc

---

## Final C# Code

```csharp
public class Solution {
    public int[] NextGreaterElement(int[] nums1, int[] nums2) {
        Stack<int> s = new Stack<int>();
        Dictionary<int,int> dict = new Dictionary<int, int>();

        for(int i = nums2.Length-1; i>=0; i--)
        {
            while(s.Count != 0 && nums2[i] > s.Peek()){
                s.Pop();
            }
            int nxtL = s.Count == 0 ? -1 : s.Peek();
            dict[nums2[i]] = nxtL;
            s.Push(nums2[i]);
        }
        int[] ans = new int[nums1.Length];

        for(int i=0; i< nums1.Length; i++){
            if(dict.ContainsKey(nums1[i])){
               ans[i] = dict[nums1[i]];
            }
            else{
                ans[i] = -1;
            }
        }

        return ans;
    }
}
```

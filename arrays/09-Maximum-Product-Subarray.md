# 🔥 Maximum Product Subarray

**LeetCode:** https://leetcode.com/problems/maximum-product-subarray/  
**Difficulty:** Medium  
**Pattern:** Dynamic Programming (Track Max & Min)

---

## 🧠 Problem Statement

Given an integer array `nums`, find a contiguous non-empty subarray within the array that has the largest product, and return that product.

---

## 💡 Examples

### Example 1
Input:
nums = [2,3,-2,4]

Output:
6

Explanation:
The subarray [2,3] has the largest product = 6.

---

### Example 2
Input:
nums = [-2,0,-1]

Output:
0

---

## 🚀 Approach

Unlike Maximum Subarray (sum), here:

- Negative × Negative = Positive
- Zero resets the product
- A small negative can become very large later

So we must track:

- `maxSoFar`
- `minSoFar`

Because the minimum product can become maximum when multiplied by a negative number.

---

## 🔎 Algorithm

1. Initialize:
   - `maxSoFar = nums[0]`
   - `minSoFar = nums[0]`
   - `result = nums[0]`

2. Iterate from index 1 to end:
   - If current number < 0 → swap `maxSoFar` and `minSoFar`
   - Update:
     - `maxSoFar = max(current, maxSoFar * current)`
     - `minSoFar = min(current, minSoFar * current)`
   - Update result:
     - `result = max(result, maxSoFar)`

3. Return result

---

## ✅ C# Solution (O(n), O(1))

```csharp
public int MaxProduct(int[] nums)
{
    int maxSoFar = nums[0];
    int minSoFar = nums[0];
    int result = nums[0];

    for (int i = 1; i < nums.Length; i++)
    {
        int current = nums[i];

        if (current < 0)
        {
            int temp = maxSoFar;
            maxSoFar = minSoFar;
            minSoFar = temp;
        }

        maxSoFar = Math.Max(current, maxSoFar * current);
        minSoFar = Math.Min(current, minSoFar * current);

        result = Math.Max(result, maxSoFar);
    }

    return result;
}

## Mistakes I Made
- started iteration first element and intialzed with first element
- then initalized with 1 wont cover 0 in array condition
- forgot to add int before x
- initilization of maxp, minp, gloabamax to first element
- make sure to add the current value in the comparision in the max and min calculation.

---

## Edge Cases
- Empty array
- Single element
- etc

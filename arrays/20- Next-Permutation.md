# Next Permutation

## [Problem Link](https://leetcode.com/problems/next-permutation)


## Difficulty
Medium 

## Pattern
(Hash Map / Two Pointer / Sliding Window / Prefix Sum / etc)

---

## Optimized Approach

### Idea
Find pivot: Scan from right to left to find the first position i where nums[i] < nums[i+1] (rightmost ascending pair)
Handle descending case: If no pivot exists (array is fully descending), reverse entire array to get smallest permutation
Reverse suffix: Reverse elements after pivot to prepare for finding swap candidate
Find swap candidate: Find smallest element after pivot that's larger than pivot element
Swap and complete: Swap pivot with candidate to get next permutation
### Time Complexity
O(n)

### Space Complexity
O(1)

---

## Key Insight
What made the optimized solution work?

---

## Mistakes I Made
-  when iterate remeber to include value in index;
- all descending order condition

---

## Edge Cases
- corner case when all are descenting
- 
---

## Final C# Code
``` C Sharp
public class Solution {
    public void NextPermutation(int[] nums) {
        // find the pivot num[i] < num[i+1]
        int l = nums.Length - 2;
        int pivot = -1;
        for( int i = l; i >= 0; i--)
        {
            if(nums[i] < nums[i+1])
            {
                pivot = i;
                break;
            }
        }
        // reverse all numbers after the pivot
            nums = Reverse(nums, pivot);
        // corner condition if the nums are descending order reverse the nums 

        // find a number that larger than pivot and smallest in the reversed number
        if(pivot != -1)
        {
            int nextLarge = int.MaxValue;;
            int ind = pivot;
            for( int i = pivot + 1; i < nums.Length; i++)
            {
                if(nums[i] > nums[pivot] && nextLarge > nums[i]){
                    ind = i;
                    nextLarge = nums[i];
                }
            }
        // swap that number with pivot
            int temp = nums[ind];
            nums[ind] = nums[pivot];
            nums[pivot] = temp;
        }
    }

    public int[] Reverse(int[] nums, int pivot)
    {
    
        int l = nums.Length - 1;
        int p = pivot + 1;
        while(p < l)
        {
            //swap;
            int temp = nums[l];
            nums[l] = nums[p];
            nums[p] =  temp;
            p++;
            l--; 
        }
        return nums;
    }
}

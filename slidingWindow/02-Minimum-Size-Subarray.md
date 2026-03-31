# Minimum Size Subarray Sum

## https://leetcode.com/problems/minimum-size-subarray-sum/

## Mistakes
- int.MaxValue . forget the correct syntax.
- window calucation add + 1 that is not need as  r++ incremented so correct is  r - l

``` csharp
 public int MinSubArrayLen(int target, int[] nums) {
        var wSize = int.MaxValue;
        int l = 0 , r = 0;
        int cSum = 0;
        while(r< nums.Length)
        {
            while( r < nums.Length && cSum < target)
            {
                cSum += nums[r];
                //wSize = Math.Min(wsize, r - l + 1);
                r++;
            }
            while( l <= r && cSum >= target)
            {
                wSize = Math.Min(wSize, r - l );
                cSum -= nums[l];
                l++;
            }            
        }
        return wSize == int.MaxValue ? 0 : wSize;
    }

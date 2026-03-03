# Best Time to Buy and Sell Stock

## https://leetcode.com/problems/best-time-to-buy-and-sell-stock


## Difficulty
Easy 

## Pattern
Greedy, Running Minimum, Kadane's Algorithm Variant
---

## Problem Summary

Given an array `prices` where `prices[i]` is the stock price on day `i`.

You must:
- Buy once
- Sell once
- Sell after buying
- Maximize profit

Return the maximum profit. If no profit possible, return 0.

---

## Greedy — Track Minimum Price (Optimal)

### Idea

Track the minimum price seen so far.

At each day:
- Assume current day is selling day
- Profit = current price − minimum price so far
- Update max profit if higher

This ensures we always buy at lowest price before selling.

---

### Example

prices = [7,1,5,3,6,4]

| Day | Price | Min Price So Far | Profit | Max Profit |
|-----|------|------------------|--------|------------|
| 0   | 7    | 7                | 0      | 0          |
| 1   | 1    | 1                | 0      | 0          |
| 2   | 5    | 1                | 4      | 4          |
| 3   | 3    | 1                | 2      | 4          |
| 4   | 6    | 1                | 5      | 5          |
| 5   | 4    | 1                | 3      | 5          |

Result = 5

---

### Time Complexity
O(n)

### Space Complexity
O(1)

---

### Final C# Code

```csharp
public class Solution {
  public int MaxProfit(int[] prices)
  {
    int minPrice = prices[0];
    int maxProfit = 0;
    for(int i=1; i<prices.Length; i++)
    {
        if(prices[i] < minPrice)
        {
          minPrice = prices[i];
        }
        else
        {
          maxProfit = Math.Max(maxProfit,prices[i] -minPrice);
        }
    }

    return maxProfit;
  }
}
```
## Kadane's Algorithm 
### Idea
Instead of tracking the min price track daily differences and find maximum subarray sum using kadane's algorithm
this work because max profit = max gain sequence

### Time Complexity
O(n)

### Space Complexity
O(1)

### Final C# Code

```csharp

public class Solution {
  public int MaxProfit(int[] prices)
  {
    int maxProfit = 0;
    int cur = 0;
    for(int i=1; i<prices.Length; i++)
    {
      int diff = prices[i] - prices[i-1];
      cur = Math.Max(0, cur+diff);
      maxProfit = Math.Max(cur,maxProfit);
    }
    return maxProfit;
  }
}
```
## Mistakes I Made
- spelling mistakes, capital letter small letter, initalizing 
- improvment with max operation,

##  Revision Notes (Important)
Track minimum price while scanning once. Profit = current price − min price.
kadane's algo 
You track two things:
currentSum → sum of current subarray
maxSum → best sum seen so far
currentSum = max(num, currentSum + num)
maxSum = max(maxSum, currentSum)


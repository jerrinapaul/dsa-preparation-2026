# Coin Change

## https://leetcode.com/problems/coin-change
Paste link here

## Difficulty
Easy / Medium / Hard

## Pattern
(Hash Map / Two Pointer / Sliding Window / Prefix Sum / etc)

---

## Bottom down approach

### Idea
<img width="1103" height="397" alt="image" src="https://github.com/user-attachments/assets/d6ffaafd-f58d-43bf-9fa8-d50b55c0b08e" />

min_coin_combination(target) = 1 + min(min_coin_combination(target - coin_i) | coin_i ∈ coins)


for (int coin : coins) {
    if (coin <= target) {
        dp[target] = Math.min(dp[target], 1 + dp[target - coin]);
    }
}
### Time complexity: 
The time complexity of min_coin_combination_bottom_up is O(targetn) because we loop through all n coins for each value between 1 and target.

### Space complexity: 
The space complexity is O(target) due to the space occupied by the DP array, which is of size target+1.


## Top down Approach

### Idea
Explain briefly

### Time Complexity
 * Without memomization the tine coplexity of MinCoinComb would be o(n^target/m) where n denotes the number of coins and m denotes the smallest coin value. The recursion tree has a branch factor of n because we make a recursive call for up tp n coins . the depth of the tree is target / m because in the wordt case we contiually reduce the target value by the smallest coin.
 * With memoization each subproblem is solved oinly once . Since there are at most target subproblems ans we iterate through all n coins for each subproblems the time complexity is O(target* n)
  ---

### Space Complexity
The space complexity is O(target) because, while the maximum depth of the recursive call stack is only target/m, the memoization array stores up to target key-value pairs.

---

## Key Insight
What made the optimized solution work?

---

## Mistakes I Made
- Missed base condition amount < 0
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
    public int CoinChange(int[] coins, int amount) {

        var res = MinCoinComb(coins, amount, new Dictionary<int, int>());
        return res != int.MaxValue? res : -1;
    }
    public int MinCoinComb(int[] coins, int amount, Dictionary<int, int> memo)
    {
        
        if(amount == 0)
        {
             return 0;
        }

        if(amount < 0) {
            return int.MaxValue;
        }
        if(memo.ContainsKey(amount))
        {
            return memo[amount];
        }
        int minCoin = int.MaxValue;
        foreach(var coin in coins)
        {            
            int subRes = MinCoinComb(coins, amount- coin, memo);
            if(subRes != int.MaxValue)
            {
                minCoin = Math.Min(1 + subRes, minCoin );
            }
        }
        memo[amount] = minCoin;
        return memo[amount];
    }
}

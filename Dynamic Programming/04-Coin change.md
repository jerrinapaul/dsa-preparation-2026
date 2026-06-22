# Coin Changee

## Problem Link
[https://neetcode.io/problems/coin-change/question]

## Difficulty
Medium

## Pattern
(recursion/ dp)

---

## Approach 1

### Idea
top-down: 
recursive 
- dfs, for amount, 
- branch for each coin, 
- cache to store prev coin_count for each amount;
bottom-up:
- compute coins for amount = 1, up until n, using for each coin (amount - coin),
- cache prev values

* "The decision tree branches into exactly two choices at each step:
*  we either take the current coin and stay at the same index to allow reuse, or
*  we skip it and move to the next coin type."
### Time Complexity
O()

### Space Complexity
O()

---
## Final C# Code

```csharp
public class Solution {
    public Dictionary<(int,int),int> dp = new Dictionary<(int,int),int>();
    public int CoinChange(int[] coins, int amount) {
        // Use amount + 1 as a safe "infinity" to avoid integer overflow
        int res = Solve(coins, 0, amount, amount + 1);
        return res > amount ? -1 : res;
    }

    public int Solve(int[] coins, int i, int t, int maxSentinel) {
        if (t == 0) return 0;
        if (i >= coins.Length || t < 0) return maxSentinel;
        if(dp.ContainsKey((i,t))) return dp[(i,t)];
        // Choice 1: Take the current coin (stay at index i)
        int take = maxSentinel;
        if (t - coins[i] >= 0) {
            take = 1 + Solve(coins, i, t - coins[i], maxSentinel);
        }

        // Choice 2: Skip the current coin (move to index i + 1)
        int notTake = Solve(coins, i + 1, t, maxSentinel);
        dp[(i,t)]=Math.Min(take, notTake); 
        return dp[(i,t)];
    }
}

## Optimized Approach

### Idea
the recursion tree represents the brute-force search space where the root is the target amount, and
each node branches into N children—one for each coin choice—with the edges representing subtracting that coin's value,
branching down until the amount reaches 0 or becomes negative."

### Time Complexity
O()

### Space Complexity
O()

---

## Mistakes I Made
- integer overflow adding 1 + it.MaxValue
- mixing up two concept together
- either use for loop for each coin or consider take the coin from current index and skip the current index

---

## Edge Cases
- return -1 
- Single element
- etc

---

## Final C# Code

```csharp
public class Solution {
    int[] dp;
    public int CoinChange(int[] coins, int amount) {
        /*
        12 ->1 -> 11 -1-> 10-1>9.....
        12-1->11-5->6
        12-1->11-1->10-10-> 0 so we got (3)
        */
        dp = new int[amount + 1];
        for(int i = 0; i <= amount; i++){
            dp[i] = -1;
        }
        var ans = Solve(coins, amount);
        return ans == int.MaxValue - 1 ? -1 : ans;
        
    }

    public int Solve(int[] coins, int target){
        if(target == 0) return 0;
        if(target < 0) return int.MaxValue - 1;
        if(dp[target] != -1) return dp[target];
        var ans = int.MaxValue - 1;
        foreach(var c in coins){
            ans = Math.Min(ans, 1 + Solve(coins,target -c) );
        }
        dp[target] = ans;
        return ans;
        

    }
    
}

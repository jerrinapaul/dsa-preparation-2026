## Climbing Stairs
Determine the number of distinct ways to climb a staircase of n steps by taking either 1 or 2 steps at a time.

#### Example:
<img width="1655" height="338" alt="image" src="https://github.com/user-attachments/assets/ee69f76d-d9d2-46fe-8f46-6febe06712ed" />
### Intuition - Top-Down

A brute force solution to this problem is to go through all possible combinations of moving 1 or 2 steps up the stairs until reaching the top. How would we do this? Think about how to get to stair i:


<img width="280" height="282" alt="image" src="https://github.com/user-attachments/assets/51d4bc4d-3f13-4724-a7b2-ba350643f5ca" />

One thing we know for sure is that to reach step i, we need to reach it from either step i - 1, or step i - 2 since we can only climb 1 or 2 steps at a time:

<img width="670" height="282" alt="image" src="https://github.com/user-attachments/assets/799b9159-edf0-4c86-b763-c53e8c8aadca" />

This is all the information we need. If we want to know all the different ways we can get to step i, we just need to know:

The number of ways to get to step i - 1 (climbing_stairs(i - 1)).
The number of ways to get to step i - 2 (climbing_stairs(i - 2)).

This highlights that this problem has an optimal substructure where, in order to solve climbing_stairs(n), we need the answers to two of its subproblems. We can translate this to a recurrence relation:

climbing_stairs(n) = climbing_stairs(n - 1) + climbing_stairs(n - 2)

Let’s first implement this using recursion.

To do this, we’ll need to identify the base cases, which handle the simplest subproblems. The simplest versions of this problem occur when the number of steps is 1 or 2. If n equals 1, we return 1 since the only way to reach step 1 is to climb 1 step. If n equals 2, return 2 since there are two ways to reach step 2.

If we apply this recursive logic to a staircase of 6 steps, this is what the recursion tree would look like:
<img width="1355" height="603" alt="image" src="https://github.com/user-attachments/assets/c66cbc87-8073-4d6c-a1fd-fd0df424d97d" />

This solution is considered a top-down solution as it starts from the main problem, and recursively breaks it down into smaller subproblems as it progresses down the recursive tree.

You may have noticed in the recursion tree that we do some repeated work by calling the same subproblem multiple times (e.g., climbing_stairs(4) is called twice). This highlights the existence of overlapping subproblems. This isn't a big issue for short staircases, but for a taller one with more steps, it can result in a lot of repeated calculations of subproblems we’ve already solved. This is where memoization comes into play.

### Memoization
Storing the result of each subproblem the first time we solve it, then reusing these stored results when needed, is a technique known as memoization. For example, after we calculate the subproblem of n = 3 (climbing_stairs(3)) for the first time, we don’t need to calculate it again; we can just fetch the already-calculated result for n = 3. The same applies to n = 4. This greatly reduces the size of the recursion tree:

<img width="1355" height="603" alt="image" src="https://github.com/user-attachments/assets/e627fac8-ceb7-4e9d-bff5-e78fef2b7d41" />

We use a hash map for memoization to store the results of subproblems for constant-time access. For example, after calculating the result for the subproblem n = 3, we store the result in the hash map as a value, where the key is 3.

As we can see, we’ve successfully implemented a DP solution using top-down memoization. We identified the subproblems, used them to create the recurrence relation, specified our base cases, and applied memoization to ensure each subproblem is solved only once.

### C sharp code
```csharp
public class Solution {
    Dictionary<int,int> memo = new Dictionary<int, int>();
    public int ClimbStairs(int n) {
        if(n<=2)
        {
            return n;
        }
        if(memo.ContainsKey(n))
        {
            return memo[n];
        }
        memo[n] = ClimbStairs(n-1) + ClimbStairs(n-2);

        return memo[n];
    }
}
```
### Intuition - Bottom-Up
Generally, any problem that can be solved using top-down memoization can also be solved using a bottom-up DP approach, where we translate the memoization array to a DP array. Let's explore how this works.

Translating the memoization array to a DP array
Think about what each value in the DP array represents. We want this array to store the answers to our subproblems (i.e., dp[i] should store the number of ways we can reach step i). Now, remember that our memoization array stores the same thing. In other words, dp[i] and memo[i] store the same result.

In our top-down implementation, the memoization stores results like so:
memo[n] = climbing_stairs(n - 1) + climbing_stairs(n - 2)

However, if the results of climbing_stairs(n - 1) and climbing_stairs(n - 2) were already calculated and memoized, this is what would actually be going on:
memo[n] = memo[n - 1] + memo[n - 2]

Now that we have this tabular relationship for the memoization array, simply change “memo” to “dp” to get the DP relationship:
dp[n] = dp[n - 1] + dp[n - 2]

We call this a bottom-up solution because we need to calculate the solutions to smaller subproblems before we can solve the larger ones. In other words, we "build up" to the main solution as opposed to the top-down solution, where we start with the main problem, n, and work our way down.

Base cases
Our base cases stay the same: the answers to dp[1] and dp[2] are 1 and 2, respectively.

Return statement
In our top-down solution, we return memo[n]. Since there’s a one-to-one relationship between the memoization array and the DP array, we can just return dp[n] in our bottom-up solution.

### Cs sharp code
```csharp
public class Solution {
   
    public int ClimbStairs(int n) {
        if(n<=2)
        {
            return n;
        }
        int[] dp = new int[n+1];
        dp[1] = 1;
        dp[2] = 2;
        for(int i = 3; i <= n ; i++)
        {
            dp[i] = dp[i-1] + dp [i-2];
        }
        return dp[n];

    }
}
``

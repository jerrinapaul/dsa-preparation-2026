# word break

## https://leetcode.com/problems/word-break

## Difficulty
 Medium

## Pattern
(Dynammic programming)

---

O()

### Space Complexity
O()

---

## Optimized Approach

### Idea
Explain briefly

### Time Complexity
O()

### Space Complexity
O()

---

## Key Insight
What made the optimized solution work?

---

## Mistakes I Made
- forget to put "="  i + wl <= s.Length calculate till s.Length 
- 

---

## Edge Cases
- Empty array
- Single element
- etc

---

## Final C# Code

```csharp public bool WordBreak(string s, IList<string> wordDict) {
        bool[] dp = new bool[s.Length + 1];
        for(int i =0; i<s.Length; i++){
            dp[i] = false;
        }
        dp[s.Length] = true;

        for(int i = s.Length-1; i>=0;i--){
            foreach(var w in wordDict){
                int wl =w.Length;
                if(i + wl <= s.Length && s.Substring(i,wl) == w ){
                        dp[i] = dp[i+ wl];
                       // Console.WriteLine("inside {0} {1} {2}",i, s[i],dp[i]);
                }
                //Console.WriteLine("{0} {1} {2}",i, s[i],dp[i]);
                if(dp[i])
                 break;
            }
        }
        return dp[0];
    }
```

# Same Binary Tree

## Problem Link
[Same Binary Tree]
## Difficulty
Easy

## Pattern
(DFS/BFS)

---

## Brute Force Approach

### Idea
recursive dfs on both trees at the same time; iterative bfs compare each level of both trees


## Mistakes I Made
- return false when one ofe the node empty or null  if(p == null || q == null) return false;
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
    public bool IsSameTree(TreeNode p, TreeNode q) {
        
        if( p== null && q == null) return true;
        if(p == null || q == null) return false;
        
        if(p.val == q.val){
            return IsSameTree(p.left,q.left) && IsSameTree(p.right, q.right);
        }
        return false;
    }
}

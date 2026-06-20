# Maximum Depth of Binary Tree

## Problem Link
https://neetcode.io/problems/depth-of-binary-tree/history?submissionIndex=2

## Difficulty
Easy 

## Pattern
(DFS/BFS)

---

## Brute Force Approach

### Idea
do DFS add 1 +Max(of left, right)
do BFS and add each level -process all element in one level

### Time Complexity
O(n)

### Space Complexity
O(1)

---

## Mistakes I Made
- BFS - remeber to keep the size in a variable
= remeber to do the null check if(root != null)
- Mistake 2

---

## Edge Cases
- remeber to add null check for root


---

## Final C# Code


```csharp
public class Solution {
    public int MaxDepth(TreeNode root) {
        //DFS
        // if(root == null) return 0;
        // return 1 + Math.Max(MaxDepth(root.left),MaxDepth(root.right));

        //BFS
        Queue<TreeNode> q = new Queue<TreeNode>();
        if(root != null)
            q.Enqueue(root);
        int level = 0;
        while (q.Count > 0) {
            int size = q.Count;
            for(int i = 0; i < size; i++){
                var cur = q.Dequeue();
                if(cur.left != null)
                    q.Enqueue(cur.left);
                if(cur.right != null)
                    q.Enqueue(cur.right);
            }
            level++;        

        }
        return level;
        
    }
}

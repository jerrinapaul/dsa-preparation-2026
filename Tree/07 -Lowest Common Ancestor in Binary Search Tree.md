# Problem Name
Lowest Common Ancestor in Binary Search Tree

## Problem Link
https://neetcode.io/problems/lowest-common-ancestor-in-binary-search-tre

## Difficulty
Medium

## Pattern
(BST property)

---

## Optimized Approach

### Idea
Explain briefly

### Time Complexity
O(n)

### Space Complexity
O(n)

---

## Key Insight
What made the optimized solution work?
dfs

---

## Mistakes I Made
- remember to return from all path at the end of the recursion for null scenario
- Mistake 2

---

## Edge Cases
- handle null scenario
- Single element
- etc

---

## Final C# Code

```csharp

public class Solution {
    public TreeNode LowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if(p.val > q.val){
            TreeNode  temp = p ;
            p = q;
            q = temp;
        }
        if(p.val < root.val && q.val > root.val) return root;
        if(root.val == p.val || root.val == q.val ) return root;
        if(p.val < root.val && q.val < root.val) return LowestCommonAncestor(root.left,p,q);
        if(p.val > root.val && q.val > root.val) return LowestCommonAncestor(root.right,p,q);
        return null;
    }
}

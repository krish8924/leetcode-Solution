---
Difficulty: Easy
Platform: LeetCode
---

# 🚀 Binary Tree Inorder Traversal

🔗 Problem Link: https://leetcode.com/problems/binary-tree-inorder-traversal/description/

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
root = [1,null,2,3]
```

**Output:**

```
[1,3,2]
Explanation: inoder then Left-Root-Right 
```

*Example 2*

**Input:**

```
root = [1,2,3,4,5,null,8,null,null,6,7,9]
```

**Output:**

```
[4,2,6,5,7,1,3,9,8]
```
## 💻 Code (Java)

```java
/*By Recursively*/
class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
        
        List<Integer> res=new ArrayList();
        helper(res, root);
        return res;
    }
    void helper(List<Integer> res, TreeNode root){
        if(root == null){
            return;
        }
        helper(res,root.left);
        res.add(root.val);
        helper(res,root.right);
    }

}
```

## 💻 Code (Java)

```java
/*By  iteratively*/

class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
        
        List<Integer> res=new ArrayList();
        Stack<TreeNode> stack =new  Stack();
        TreeNode curr = root;
        while(curr != null || !stack.isEmpty()){
            while(curr != null){
                stack.push(curr);
                curr=curr.left;
            }
            curr=stack.pop();
            res.add(curr.val);
            curr=curr.right;

        }
        return res;
    } 
}
```

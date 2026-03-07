---
Difficulty: Easy
Platform: LeetCode
---

# 🚀 Climbing Stairs

🔗 Problem Link: https://leetcode.com/problems/climbing-stairs/description/

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
n = 2
```

**Output:**

```
2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps
```

*Example 2*

**Input:**

```
n = 3
```

**Output:**

```
3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
```
## 💻 Code (Java)

```java
class Solution {
    public int removeElement(int[] nums, int val) {
      int k=0;
      for(int i=0;i<nums.length;i++)
      {
        if(nums[i]!=val)
        {
            nums[k]=nums[i];
            k++;
        }
      } 
      return k; 
    }
}
```

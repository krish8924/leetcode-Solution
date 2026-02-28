---
Difficulty: Easy
Platform: LeetCode
---

# 🚀 Longest Common Prefix

🔗 Problem Link: https://leetcode.com/problems/longest-common-prefix/description/

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
strs = ["flower","flow","flight"]
```

**Output:**

```
"fl"
```

*Example 2*

**Input:**

```
strs = ["dog","racecar","car"]
```

**Output:**

```
""
Explanation: There is no common prefix among the input strings.
```
## 💻 Code (Java)

```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        if (strs == null || strs.length == 0) {
            return "";
        }
        
        String prefix = strs[0];   
        
        for (int i = 1; i < strs.length; i++) {
            
            int j = 0;
            
            while (j < prefix.length() &&
                   j < strs[i].length() &&
                   prefix.charAt(j) == strs[i].charAt(j)) {
                j++;
            }
            
            prefix = prefix.substring(0, j);
            if (prefix.isEmpty()) {
                return "";
            }
        }
        return prefix;
    }
}
```

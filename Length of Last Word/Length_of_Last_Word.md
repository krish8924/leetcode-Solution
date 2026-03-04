---
Difficulty: Easy
Platform: LeetCode
---

# 🚀 Length of Last Word

🔗 Problem Link: https://leetcode.com/problems/length-of-last-word/description/

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
s = "Hello World"
```

**Output:**

```
5
Explanation: The last word is "World" with length 5.
```

*Example 2*

**Input:**

```
s = "   fly me   to   the moon  "
```

**Output:**

```
4
Explanation: The last word is "moon" with length 4.
```
## 💻 Code (Java)

```java
class Solution {
    public int lengthOfLastWord(String s) {
      int temp=0;
		int count=0;
		  for(int i = s.length()-1; i >= 0; i--)
        {
            if(s.charAt(i) != ' ')
                count++;
            else if(count > 0)
                break;
        }
        return count;  
    }
}
```

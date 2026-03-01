---
Difficulty: Easy
Platform: LeetCode
---

# 🚀 Valid Parentheses

🔗 Problem Link: https://leetcode.com/problems/valid-parentheses/description/

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
s = "()"
```

**Output:**

```
true
```

*Example 2*

**Input:**

```
s = "()[]{}"
```

**Output:**

```
true
```

*Example 3*

**Input:**

```
s = "([)]"
```

**Output:**

```
false
```
## 💻 Code (Java)

```java
import java.util.*;

class Solution {
    public boolean isValid(String s) {

        Stack<Character> stack = new Stack<>();

        for(int i = 0; i < s.length(); i++) {

            char ch = s.charAt(i);

            // opening brackets
            if(ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
            } 
            else {
                // no matching opening bracket
                if(stack.isEmpty())
                    return false;

                char top = stack.pop();

                // check matching pair
                if((ch == ')' && top != '(') ||
                   (ch == '}' && top != '{') ||
                   (ch == ']' && top != '[')) {
                    return false;
                }
            }
        }

        // stack must be empty
        return stack.isEmpty();
    }
}
```

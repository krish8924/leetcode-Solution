---
Difficulty: Medium 
Platform: LeetCode
---

# 🚀 Reverse Integer

🔗 Problem Link: https://leetcode.com/problems/reverse-integer/

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
x = 123
```

**Output:**

```
321
```

*Example 2*

**Input:**

```
x = -123
```

**Output:**

```
-321
```
## 💻 Code (Java)

```java
class Solution {
    public int reverse(int x) {
        int result = 0;

        while (x != 0) {
            int digit = x % 10;
            x /= 10;

            int newResult = result * 10 + digit;

         
            if ((newResult - digit) / 10 != result) {
                return 0;
            }

            result = newResult;
        }

        return result;
    }
}
```

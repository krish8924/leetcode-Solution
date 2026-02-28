---
Difficulty: Easy
Platform: LeetCode
---

# 🚀 Palindrome Number

🔗 Problem Link: https://leetcode.com/problems/palindrome-number/description/

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
x = 121
```

**Output:**

```
true
Explanation: 121 reads as 121 from left to right and from right to left.
```

*Example 2*

**Input:**

```
x = -121
```

**Output:**

```
false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```
## 💻 Code (Java)

```java
class Solution {
    public boolean isPalindrome(int x) {
        if(x < 0)
        {
            return false;
        }
        if(x < 10)
        {
            return true;
        }
        int n = x;
        int reverse = 0;
        
        while(n > 0)
        {
            reverse = reverse * 10 + n % 10;
            n = n / 10;
        }
        if(reverse == x )
        {
            return true;
        }
        else
        {
            return false; 
        }
    }
}
```

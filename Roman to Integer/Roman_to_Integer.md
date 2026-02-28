---
Difficulty: Easy
Platform: LeetCode
---

# 🚀 Roman to Integer 

🔗 Problem Link: https://leetcode.com/problems/roman-to-integer/

**Seven different symbols represent Roman numerals with the following values:**
---

| Symbols  | Values |
| ---------| -------|
| `I`      |   1    |
| `V`      |   5    |
| `X`      |   10   |
| `L`      |   50   |
| `C`      |   100  |
| `D`      |   500  |
| `M`      |   1000 |

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
s = "III"
```

**Output:**

```
3
Explanation: III = 3.
```

*Example 2*

**Input:**

```
s = "LVIII"
```

**Output:**

```
58
Explanation: L = 50, V= 5, III = 3.
```
## 💻 Code (Java)

```java
class Solution {
    public int romanToInt(String s) {
        
        int total = 0;
        
        for(int i = 0; i < s.length(); i++) {
            
            int current = value(s.charAt(i));
            
            if(i < s.length() - 1) {
                int next = value(s.charAt(i + 1));
                
                if(current < next) {
                    total -= current;
                } else {
                    total += current;
                }
            } else {
                total += current;
            }
        }
        
        return total;
    }
    
    public int value(char ch) {
        switch(ch) {
            case 'I': return 1;
            case 'V': return 5;
            case 'X': return 10;
            case 'L': return 50;
            case 'C': return 100;
            case 'D': return 500;
            case 'M': return 1000;
        }
        return 0;
    }
}
```

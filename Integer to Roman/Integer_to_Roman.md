---
Difficulty: Easy
Platform: LeetCode
---

# 🚀 Integer to Roman

🔗 Problem Link: https://leetcode.com/problems/integer-to-roman/description/

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
num = 3749
```

**Output:**

```
"MMMDCCXLIX"

Explanation:
3000 = MMM as 1000 (M) + 1000 (M) + 1000 (M)
700 = DCC as 500 (D) + 100 (C) + 100 (C)
40 = XL as 10 (X) less of 50 (L)
9 = IX as 1 (I) less of 10 (X)
Note: 49 is not 1 (I) less of 50 (L) because the conversion is based on decimal places
```

*Example 2*

**Input:**

```
num = 58
```

**Output:**

```
"LVIII"
Explanation: 50 = L, 8 = VIII
```
## 💻 Code (Java)

```java
class Solution {
    public String intToRoman(int num) {
        
        int[] values = {
            1000, 900, 500, 400,
            100, 90, 50, 40,
            10, 9, 5, 4, 1
        };
        
        String[] symbols = {
            "M", "CM", "D", "CD",
            "C", "XC", "L", "XL",
            "X", "IX", "V", "IV", "I"
        };
        
        StringBuilder result = new StringBuilder();
        
        for(int i = 0; i < values.length; i++) {
            while(num >= values[i]) {
                result.append(symbols[i]);
                num -= values[i];
            }
        }
        
        return result.toString();
    }
}
```

---
Difficulty: Easy
Platform: LeetCode
---

# 🚀 Sqrt(x)

🔗 Problem Link: https://leetcode.com/problems/sqrtx/description/

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
x = 4
```

**Output:**

```
2
Explanation: The square root of 4 is 2, so we return 2.
```

*Example 2*

**Input:**

```
x = 8
```

**Output:**

```
5

Explanation: The square root of 8 is 2.82842..., and since we round it down to the nearest integer, 2 is returned.
```
## 💻 Code (Java)

```java
class Solution {
    public int mySqrt(int x) {
        long low=0;
        long high=x;
        long ans=0;
        while(low<=high){
            long mid=(high+low)/2;
            if(mid*mid==x){
                return (int)mid;
            }
            else if(mid*mid<x){
                low=mid+1;
                ans=mid;
            }
            else{
                high=mid-1;
            }

        }
    return (int)ans; 
    }
}
```

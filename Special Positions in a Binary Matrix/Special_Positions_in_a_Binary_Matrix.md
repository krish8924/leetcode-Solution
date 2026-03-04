---
Difficulty: Easy
Platform: LeetCode
---

# 🚀 Special Positions in a Binary Matrix

🔗 Problem Link: https://leetcode.com/problems/special-positions-in-a-binary-matrix/description/

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
-------------
| 1 | 0 | 0 |
-------------
| 0 | 0 | 1 |
-------------
| 1 | 0 | 0 |
-------------

mat = [[1,0,0],[0,0,1],[1,0,0]]
```

**Output:**

```
1
Explanation: (1, 2) is a special position because mat[1][2] == 1 and all other elements in row 1 and column 2 are 0.
```

*Example 2*

**Input:**

```
-------------
| 1 | 0 | 0 |
-------------
| 0 | 1 | 0 |
-------------
| 0 | 0 | 1 |
-------------

mat = [[1,0,0],[0,1,0],[0,0,1]]
```

**Output:**

```
3
Explanation: (0, 0), (1, 1) and (2, 2) are special positions.
```
## 💻 Code (Java)

```java
class Solution {
    public int numSpecial(int[][] mat) {
    int m = mat.length;
    int n = mat[0].length;

    int[] row = new int[m];
    int[] col = new int[n];

    for(int i=0; i<m; i++){
        for(int j=0; j<n; j++){
            if(mat[i][j] == 1){
            row[i]++;
            col[j]++;} 
        }
    }

    int count = 0;

    for(int i=0; i<m; i++){
        for(int j=0; j<n; j++){
           if(mat[i][j] == 1){
            if(row[i] == 1 && col[j] == 1)
            {
                count++;
            }
           }

        }
    }
    return count;
    }
}
```

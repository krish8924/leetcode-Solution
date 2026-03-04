---
Difficulty: Easy
Platform: LeetCode
---

# 🚀 Search Insert Position

🔗 Problem Link: https://leetcode.com/problems/search-insert-position/description/

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
nums = [1,3,5,6], target = 5
```

**Output:**

```
2
```

*Example 2*

**Input:**

```
nums = [1,3,5,6], target = 2
```

**Output:**

```
1
```

*Example 3*

**Input:**

```
nums = [1,3,5,6], target = 7
```

**Output:**

```
4
```
## 💻 Code (Java)

```java
class Solution {
    public int searchInsert(int[] nums, int target) {
         int left = 0;
        int right = nums.length - 1;

        while (left <= right) {
        // Using this formula avoids potential integer overflow
            int mid = left + (right - left) / 2;

            if (nums[mid] == target) {
                return mid; // Target found
            }
            if (nums[mid] < target) {
                left = mid + 1; // Search right half
            } else {
                right = mid - 1; // Search left half
            }
        }
        return left;// for this program only and for binary search it is -1
        // Target not found
    }
    }
```

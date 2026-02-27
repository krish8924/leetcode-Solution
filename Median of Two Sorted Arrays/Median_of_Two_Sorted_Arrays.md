---
Difficulty: Hard
Platform: LeetCode
---

# 🚀 Median of Two Sorted Arrays

🔗 Problem Link: https://leetcode.com/problems/median-of-two-sorted-arrays/description/

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
nums1 = [1,3], nums2 = [2]
```

**Output:**

```
2.00000
Explanation: merged array = [1,2,3] and median is 2.
```

*Example 2*

**Input:**

```
nums1 = [1,2], nums2 = [3,4]
```

**Output:**

```
2.50000
merged array = [1,2,3,4] and median is (2 + 3) / 2 = 2.5.
```
## 💻 Code (Java)

```java
class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        
        if (nums1.length > nums2.length) {
            return findMedianSortedArrays(nums2, nums1);
        }

        int x = nums1.length;
        int y = nums2.length;
        
        int start = 0, end = x;
        
        while (start <= end) {
            
            int partX = (start + end) / 2;
            int partY = (x + y + 1) / 2 - partX;

            int maxLX = (partX == 0) ? Integer.MIN_VALUE : nums1[partX - 1];
            int minRX = (partX == x) ? Integer.MAX_VALUE : nums1[partX];

            int maxLY = (partY == 0) ? Integer.MIN_VALUE : nums2[partY - 1];
            int minRY = (partY == y) ? Integer.MAX_VALUE : nums2[partY];

            if (maxLX <= minRY && maxLY <= minRX) {

                if ((x + y) % 2 == 0) {
                    return (Math.max(maxLX, maxLY) + Math.min(minRX, minRY)) / 2.0;
                } else {
                    return Math.max(maxLX, maxLY);
                }
            }
            else if (maxLX > minRY) {
                end = partX - 1;
            }
            else {
                start = partX + 1;
            }
        }
    return 0;
    }
}
```

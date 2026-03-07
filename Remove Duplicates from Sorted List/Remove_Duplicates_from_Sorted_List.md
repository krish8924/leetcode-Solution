---
Difficulty: Easy
Platform: LeetCode
---

# 🚀 Remove Duplicates from Sorted List

🔗 Problem Link: https://leetcode.com/problems/remove-duplicates-from-sorted-list/description/

---
## 🔍 **Example Walkthrough:**

*Example 1*

**Input:**

```
head = [1,1,2]
```

**Output:**

```
[1,2]
```

*Example 2*

**Input:**

```
head = [1,1,2,3,3]
```

**Output:**

```
[1,2,3]
```
## 💻 Code (Java)

```java
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        if(head==null) return head;
        ListNode prev=head,curr=head.next;
        while(curr!=null){
            if(prev.val==curr.val){
                prev.next=curr.next;
                curr=curr.next;

            }
            else{
                prev=curr;
                curr=curr.next;
          }
        }
        return head;
    }
}
```

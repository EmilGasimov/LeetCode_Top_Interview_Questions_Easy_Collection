## Linked List Cycle

Given a linked list, determine if it has a cycle in it.

To represent a cycle in the given linked list, we use an integer pos which represents the position (0-indexed) in the linked list where tail connects to. If pos is -1, then there is no cycle in the linked list.

#### Example 1:
Input: `head = [3,2,0,-4], pos = 1`

Output: `true`

Explanation: There is a cycle in the linked list, where tail connects to the second node.

![image](https://assets.leetcode.com/uploads/2018/12/07/circularlinkedlist.png)

### Solution
This solution is based on [Floyd's cycle finding algorithm](https://en.wikipedia.org/wiki/Cycle_detection#Floyd's_Tortoise_and_Hare).
```java
public class Solution {
    public boolean hasCycle(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        while(fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if(slow == fast) return true;
        }
        return false;
    }
}
```

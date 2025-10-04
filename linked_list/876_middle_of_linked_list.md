Leetcode question number-876


Leetcode submission link-https://leetcode.com/problems/middle-of-the-linked-list/submissions/1790798085/


```java

class Solution {
    public ListNode middleNode(ListNode head) {
    ListNode slow = head , fast = head;
    while(fast != null && fast.next != null){
        fast = fast.next.next;
        slow = slow.next;
    }
    return slow;
}
}

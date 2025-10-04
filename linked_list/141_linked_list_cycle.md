Leetcode question number-141


Leetcode submission link-https://leetcode.com/problems/linked-list-cycle/submissions/1790788008/


```java

public class Solution {
    public boolean hasCycle(ListNode head) {
    ListNode slow = head , fast = head ;
    if(head == null || head.next == null) return false;
    while(fast !=null && fast.next != null){
        fast = fast.next.next;
        slow = slow.next;
        if(fast == slow ) return true;
    }
    return false;
}
}

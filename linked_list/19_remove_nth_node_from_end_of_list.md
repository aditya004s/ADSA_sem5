Leetcode question number-19


Leetcode submission link-https://leetcode.com/problems/remove-nth-node-from-end-of-list/submissions/1790791786/


```java

class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {
    ListNode ead = new ListNode();
    ead.next = head;
    ListNode slow = ead;
    ListNode fast = ead;
    for(int i = 0; i<n; i++){
        fast = fast.next;
    }
    while(fast.next!=null){
        slow = slow.next;
        fast = fast.next;
    }
    slow.next = slow.next.next;
    return ead.next;

}
}

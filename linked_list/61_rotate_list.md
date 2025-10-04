Leetcode question number-61


Leetcode submission link-https://leetcode.com/problems/rotate-list/submissions/1790797024/


```java

class Solution {
    public ListNode rotateRight(ListNode head, int k) {
    if (head == null || head.next == null || k == 0) return head;
    ListNode curr = head ,slow = head , fast = head;
    int l = 0;
    while(curr!=null){
        l++;
        curr = curr.next;
    }
    k = k%l;
    for(int i=0; i<k; i++) fast = fast.next;
    while(fast!=null && fast.next!=null){
        slow = slow.next;
        fast = fast.next;
    }
    fast.next = head;
    head = slow.next;
    slow.next = null;
    return head;
}
}

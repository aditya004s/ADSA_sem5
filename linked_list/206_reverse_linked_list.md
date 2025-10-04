Leetcode question number-206


Leetcode submission link-https://leetcode.com/problems/reverse-linked-list/submissions/1790792762/


```java

class Solution {
    public ListNode reverseList(ListNode head) {
    ListNode prev = null , curr = head , next ;
    while(curr!=null){
        next = curr.next;
        curr.next = prev;

        prev = curr;
        curr = next;
    }
    return prev;
}
}

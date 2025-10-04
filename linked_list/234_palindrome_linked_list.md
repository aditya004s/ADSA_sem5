Leetcode question number-234


Leetcode submission link-https://leetcode.com/problems/palindrome-linked-list/submissions/1790793668/


```java

class Solution {
    public boolean isPalindrome(ListNode head) {
    if(head == null) return true;
    ListNode slow=head , fast = head;
    while(fast!=null && fast.next != null){
        slow = slow.next;
        fast = fast.next.next;
    }
    ListNode l2 = rev(slow);
    return check(head , l2);
}
public ListNode rev(ListNode head){
    ListNode prev = null , curr = head , next;
    while(curr != null){
        next = curr.next;
        curr.next = prev;

        prev = curr;
        curr = next;
    }
    return prev;
}
public boolean check(ListNode A , ListNode B){
    while(B != null){
        if(A.val != B.val) return false;
        A = A.next;
        B = B.next;
    }
    return true;
}
}

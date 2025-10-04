Leetcode question number-160


Leetcode submission link-https://leetcode.com/problems/intersection-of-two-linked-lists/submissions/1790790180/


```java

public class Solution {
    public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
    int l1 = 0, l2 = 0;
    ListNode a = headA, b = headB;

    while (a != null) { l1++; a = a.next; }
    while (b != null) { l2++; b = b.next; }

    int diff = Math.abs(l1 - l2);

    if (l1 > l2) headA = move(headA, diff);
    else headB = move(headB, diff);

    return check(headA, headB);
}
public ListNode move(ListNode A,int k){
    while(k>0 && A != null){
        A = A.next;
        k--;
    }
    return A;
}
public ListNode check(ListNode A ,ListNode B){
    if(A == null || B == null) return null;
    while(A != null){
        if(A == B) return A;
        A = A.next;
        B = B.next;
    }
    return null;
}
}

Leetcode question number-25


Leetcode submission link-https://leetcode.com/problems/reverse-nodes-in-k-group/submissions/1790796111/


```java

class Solution {
    public ListNode reverseKGroup(ListNode head, int k) {
    ListNode temp = head , prevNode = null , nextNode;
    while(temp != null){
        ListNode kNode = kthNode(temp , k);
        if(kNode == null){
            if(prevNode != null) prevNode.next = temp;
            break;
        }
        nextNode = kNode.next;
        kNode.next = null;
        ListNode newHead = rev(temp);
        if(temp == head){
            head = newHead;
        }else{
            prevNode.next = newHead;
        }
        prevNode = temp;
        temp = nextNode;
    }
    return head;
}

public ListNode kthNode(ListNode temp , int k){
    k--;
    while(temp != null && k > 0){
        temp = temp.next;
        k--;
    }
    return temp;
}

public ListNode rev(ListNode head){
    ListNode curr = head , prev = null , next;
    while(curr != null){
        next = curr.next;
        curr.next = prev;
        prev = curr;
        curr = next;
    }
    return prev;
}
}

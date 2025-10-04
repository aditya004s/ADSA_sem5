Leetcode question number-138


Leetcode submission link-https://leetcode.com/problems/copy-list-with-random-pointer/submissions/1790786518/


```java
/*
// Definition for a Node.
class Node {
    int val;
    Node next;
    Node random;

    public Node(int val) {
        this.val = val;
        this.next = null;
        this.random = null;
    }
}
*/

class Solution {
    public Node copyRandomList(Node head) {
    if(head == null) return null;

    Node temp = head;
    while(temp != null){
        Node newNode = new Node(temp.val);
        newNode.next = temp.next;
        temp.next = newNode;
        temp = temp.next.next;
    }
    temp = head;
    while(temp != null){
        if(temp.random != null){
            temp.next.random = temp.random.next;
        }
        temp = temp.next.next;
    }
    temp = head;
    Node dummy = head.next;
    while(temp != null){
        Node copy = temp.next;
        temp.next = copy.next;
        if(copy.next != null){
            copy.next = copy.next.next;
        }
        temp = temp.next;
    }
    return dummy;
}
}

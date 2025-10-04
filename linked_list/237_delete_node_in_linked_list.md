Leetcode question number-237


Leetcode submission link-https://leetcode.com/problems/delete-node-in-a-linked-list/submissions/1790795318/


```java

class Solution {
    public void deleteNode(ListNode node) {
    node.val = node.next.val;
    node.next = node.next.next;
}
}

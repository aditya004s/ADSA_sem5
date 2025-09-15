Leetcode Question Number-169 

Leetcode link-https://leetcode.com/problems/majority-element/submissions/1771010157/

Approach of this question is start a for loop, and whenever the same element appears, increase the counter. If it’s a different element, decrease the counter. When the counter becomes zero, replace the current element with the one that now has zero frequency.


class Solution {
public int majorityElement(int[] num) {
    int a = num[0];
    int count =0;
    for(int i : num){
        if (count == 0) {
            a = i;
            count = 1;
        } else if (i == a) {
            count++;
        } else {
            count--;
        }
    }
    return a;
}
};

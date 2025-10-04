Leetcode question number-229


Leetcode submission link-https://leetcode.com/problems/majority-element-ii/submissions/1790749105/

```java
class Solution {
    public List<Integer> majorityElement(int[] nums) {

    int a1 = Integer.MIN_VALUE;
    int a2 = Integer.MIN_VALUE;
    int b1 = 0 , b2 = 0;
    List<Integer> arr = new ArrayList<>();
    for(int a : nums){
        if(b1 == 0 && a != a2){
            b1++;
            a1 = a;
        }else if(b2 == 0 && a != a1) {
            b2++;
            a2 = a;
        }else if (a1  == a) {b1++;}
        else if (a2 == a) {b2++;}
        else {b1--; b2--;}
    }
    b1 = 0;
    b2 = 0;
    for (int a : nums) {
        if (a == a1) b1++;
        else if (a == a2) b2++;
    }
    int freq  = (nums.length)/3;
    if (b1>freq) arr.add(a1);
    if(b2>freq) arr.add(a2);
    return arr;
}
}

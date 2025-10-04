Leetcode question number-53


Leetcode submission link-https://leetcode.com/problems/maximum-subarray/submissions/1790754428/

```java
class Solution {
    public int maxSubArray(int[] nums) {
    int max = Integer.MIN_VALUE;
    int sum = 0;
    for(int c : nums){
        sum += c;
         if (sum > max) max = sum;
        if (sum<0) sum = 0;
       
    }
    return max;
}
}

Leetcode question number-1004


Leetcode submission link-https://leetcode.com/problems/max-consecutive-ones-iii/submissions/1790759884/

Approach-We have to iterate a pointer till length of array.Then find the number of zeros with a count.After that remove the elements by increasing pointer only if count is greater than k where k is the number of flips.If there is 0 on ith position during removal then decrease the value of count before iteration.



```java
class Solution {
    public int longestOnes(int[] nums, int k) {
    int i=0 , j=0 , cnt = 0 , max = Integer.MIN_VALUE;
    while(j<nums.length){
        if(nums[j]==0) cnt++;
        while(cnt>k){
            if(nums[i]==0) cnt--;
            i++;
        }
        int size = j-i+1;
        if(max<size) max = size;
        j++;
    }
    return max==Integer.MIN_VALUE?0:max;
}
}

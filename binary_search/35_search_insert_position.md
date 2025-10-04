Leetcode question number-35


Leetcode submission link-https://leetcode.com/problems/search-insert-position/submissions/1790777372/


```java
class Solution {
    public int searchInsert(int[] nums, int target) {
    int s = 0 , e = nums.length-1;
    while(s<=e){
        int mid = s + ((e-s)/2);
        if(nums[mid]==target) return mid;
        else if(nums[mid]<target) s = mid+1;
        else e = mid-1;
    }
    return s;
}
}

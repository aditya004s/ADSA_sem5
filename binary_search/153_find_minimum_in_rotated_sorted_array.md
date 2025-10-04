Leetcode question number-153


Leetcode submission link-https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/submissions/1777701174/


```java
class Solution {
    public int findMin(int[] nums) {
        int start=0,end=nums.length-1;
        while(start<end){
            int mid=(start+end)/2;
            
            if(nums[mid]<=nums[end]){
                end=mid;
            }
            else{
                start=mid+1;
            }
        }
        return nums[start];
    }
}

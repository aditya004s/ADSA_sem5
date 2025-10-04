Leetcode question number-81


Leetcode submisson link-https://leetcode.com/problems/search-in-rotated-sorted-array-ii/submissions/1790783151/


```java
class Solution {
    public boolean search(int[] nums, int target) {
        int start=0,end=nums.length-1;
        while(start<=end){
            int mid=(start+end)/2;
            
            if(nums[mid]==target){
                return true;
            }
            else if(nums[start]==nums[mid] && nums[mid]==nums[end]){
                start+=1;
                end-=1;
            }
            else if(nums[start]<=nums[mid]){
                if(target>=nums[start] && target<=nums[mid]){
                    end=mid-1;
                } 
                else{
                    start=mid+1;
                }
            }
            else{
                if(target>=nums[mid] && target<=nums[end]){
                    start=mid+1;
                }
                else{
                    end=mid-1;
                }
            }
        }
        return false;
    }
}

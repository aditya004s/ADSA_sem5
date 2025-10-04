Leetcode question number-34


Leetcode submission link-https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/submissions/1790775571/


```java
class Solution {
    public int[] searchRange(int[] nums, int target) {
    int[] arr = {-1,-1};
    arr[0] = first(nums,target);
    arr[1] = last(nums,target);
    return arr;
}
public int first(int[] nums , int target){
    int first = -1;
    int s = 0;
    int e = nums.length-1;
    while(s<=e){
        int mid = s + (e-s)/2;
        if(nums[mid]==target) {first = mid; e = mid- 1;}
        else if(nums[mid]<target) {s = mid+1;}
        else {e = mid- 1;}
    }
    return first;
}
public int last(int[] nums , int target){
    int last = -1;
    int s = 0;
    int e = nums.length-1;
    while(s<=e){
        int mid = s + (e-s)/2;
        if(nums[mid]==target) {last = mid; s = mid+ 1;}
        else if(nums[mid]>target) {e = mid-1;}
        else {s = mid + 1;}
    }
    return last;
}
}

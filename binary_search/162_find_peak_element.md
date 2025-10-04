Leetcode question number-162


Leetcode submission link-https://leetcode.com/problems/find-peak-element/submissions/1790773659/



```java
class Solution {
    public int findPeakElement(int[] arr) {
    int n = arr.length;
    if(n==1) return 0;
    if(arr[n-1]>arr[n-2]) return n-1;
    if(arr[0]>arr[1]) return 0;
    int low = 1 , high = n-2;
    while(low<=high){
        int mid = low + (high-low)/2;
        if(arr[mid]>arr[mid-1] && arr[mid]>arr[mid+1]){
            return mid;
        }else if(arr[mid]>arr[mid-1]){
            low = mid+1;
        }else high = mid-1;
    }
    return -1;
    
}
}

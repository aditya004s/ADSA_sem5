Leetcode question number-74


Leetcode submission link-https://leetcode.com/problems/search-a-2d-matrix/submissions/1790781703/


```java
class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
    int r = matrix.length,c =matrix[0].length;
    int size = (r*c)-1;
    int s  = 0, e = size;
    while(s<=e){ 
        int mid = s + (e-s)/2;
        int ele = matrix[mid/c][mid%c];
        if(target == ele){
            return true;
        }else if(target < ele){
            e = mid-1;
        }else{ s = mid+1;}
    }
    return false;

}
}

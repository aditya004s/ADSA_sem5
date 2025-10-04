Leetcode question number-80

Leetcode submission link-https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/submissions/1790756068/


```java
class Solution {
    public int removeDuplicates(int[] nums) {
    int i=1;
    int c = 1;
    for(int k=1; k<nums.length; k++){
        if (nums[k]==nums[k-1]){
            if(c<2){
                c++;
                nums[i] = nums[k];
                i++;
            }
        }else{
            c = 1;
            nums[i] = nums[k];
            i++;
        }
    }
    return i;
}
}

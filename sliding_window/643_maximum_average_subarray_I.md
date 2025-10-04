Leetcode question number-643


Leetcode submission link-https://leetcode.com/problems/maximum-average-subarray-i/submissions/1790766915/


```java
class Solution {
    public double findMaxAverage(int[] nums, int k) {
        double c_sum=0;
        for(int i=0;i<k;i++){
            c_sum=c_sum+nums[i];
        }
        double max=c_sum/k;
        int n=nums.length;
        for(int j=k;j<n;j++){
            c_sum+=nums[j]-nums[j-k];
            double avg =c_sum/k;
            if (avg>max){
                max=avg;
            }
        }
        
        return max;
    }
}

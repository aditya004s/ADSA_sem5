Leetcode question number-1011


Leetcode submission link-https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/submissions/1790770775/


```java
class Solution {
    public int shipWithinDays(int[] weights, int days) {
    int ans = 0;
    int s = 0 , e = 0;
    for(int i : weights){
        s = Math.max(s,i);
        e += i;
    }
    while(s<=e){
        int mid = s + (e-s)/2;
        int d = 1;
        int sum =0 ;
        for (int w : weights) {
            if (sum + w > mid) {
                d++;
                sum = 0;
            }
            sum += w;
        }
        if(d<=days) {
            ans = mid ;
            e = mid-1;
        }else{
            s = mid+1;
        }
    }
    return ans;
}
}

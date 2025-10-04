Leetcode question number-441


Leetcode submission link-https://leetcode.com/problems/arranging-coins/submissions/1790778612/


```java
class Solution {
    public int arrangeCoins(int n) {
    long start = 0;
    long end = n;
    while(start<=end)
    {
        long mid = start + (end - start)/2;
        long sq = (mid*(mid+1))/2;
        if (sq == n ){
            return (int)mid;
        } else if (sq<n) {
            start = mid + 1;
        } else{
            end = mid-1;
        }
    }
    return (int)end;   
}
}

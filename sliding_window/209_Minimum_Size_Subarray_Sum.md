Leetcode Question Number-209

Leetcode link-https://leetcode.com/problems/minimum-size-subarray-sum/submissions/1771019973/

Approach of this question is Move the j pointer until the end of the array, keeping track of the window sum. Whenever the sum becomes greater than or equal to the target:
      Check if the current window size is smaller than the minimum found so far, then update min with j - i + 1.
      Shrink the window by moving the i pointer forward and subtracting that element from the sum.
Finally, return min if it was updated; otherwise, return 0.


class Solution {
    public int minSubArrayLen(int target, int[] num) {
        int sum = 0;
        int i = 0, j = 0, min = Integer.MAX_VALUE;

        while (j < num.length) {
            sum += num[j];

            while (sum >= target) {
                int size = j - i + 1;
                if (min > size) {
                    min = size;
                }
                sum -= num[i];
                i++;
            }
            j++;
        }

        return min == Integer.MAX_VALUE ? 0 : min;
    }
}


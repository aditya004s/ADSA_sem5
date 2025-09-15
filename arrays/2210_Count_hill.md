Leetcode Question Number-2210

Leetcode link-https://leetcode.com/problems/count-hills-and-valleys-in-an-array/submissions/1771014883/

Approach of this question is make a list of unique elements, then check each one against the element next to it.

```java
class Solution {
    public int countHillValley(int[] num) {
    int a = 0;
    ArrayList<Integer> array = new ArrayList<>();
    array.add(num[0]);
    for(int i=1; i<num.length; i++){
        if (num[i]==num[i-1]) continue;
        array.add(num[i]);
    }
    for(int i=1; i<array.size()-1; i++){
        if (array.get(i-1) < array.get(i) && array.get(i) > array.get(i+1)) a++;
        if (array.get(i-1) > array.get(i) && array.get(i) < array.get(i+1)) a++;
    }
    return a;
}
}

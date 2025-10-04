Leetcode question number-3


Leetcode submission link-https://leetcode.com/problems/longest-substring-without-repeating-characters/submissions/1790765739/


```java
class Solution {
    public int lengthOfLongestSubstring(String s) {
    HashMap<Character,Integer> mpp = new HashMap<>();
    int i=0 , j=0 , max = 0;
    while(j<s.length()){
        mpp.put(s.charAt(j), mpp.getOrDefault(s.charAt(j), 0) + 1);
        while((j-i+1)>mpp.size()){
            mpp.put(s.charAt(i),mpp.get(s.charAt(i))-1);
            if(mpp.get(s.charAt(i))==0) mpp.remove(s.charAt(i));
            i++;
        }
        if((j-i+1)== mpp.size() && max <= mpp.size()) max = mpp.size();
        j++;
    }
    return max;
}
}

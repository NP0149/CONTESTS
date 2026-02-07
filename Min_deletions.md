# Minimum deletions to make balanced string

[Problem Link](https://leetcode.com/problems/minimum-deletions-to-make-string-balanced/description/?envType=daily-question&envId=2026-02-07)

```
class Solution {
    public int minimumDeletions(String s) {
        int bcount=0;
        int deletions=0;
        for(int i=0;i<s.length();i++){
            char ch=s.charAt(i);
            if(ch=='b'){
             bcount++;
            }
            else{
              deletions=Math.min(deletions+1,bcount);
            }
        }
        return deletions;
    }
}
```
# Complexity Analysis

Time:O(N)

Space:O(1)

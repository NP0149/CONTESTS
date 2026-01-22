# Minimum number of replacements

[Problem Link](https://leetcode.com/problems/minimum-replacements-to-sort-the-array/)

```
class Solution {
    public long minimumReplacement(int[] arr) {
        long op=0;
        int n=arr.length;
        int limit=arr[n-1];
        for(int i=n-2;i>=0;i--){
            if(arr[i]<=limit){
                limit=arr[i];
            }
            else{
                int parts=(int)Math.ceil((double)arr[i]/limit);
                 //we can do this in this way also
                  // int parts=(arr[i]+limit-1)/limit;
                op+=parts-1;
               limit=arr[i]/parts;
            }
        }
        return op;
    }
}
```
# Compelxity Analysis

Time:O(n)

Space;O(1)

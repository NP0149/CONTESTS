# Find middle index

[Problem Link](https://leetcode.com/problems/find-the-middle-index-in-array/description/)

```
class Solution {
    public int findMiddleIndex(int[] nums) {
        int prefixsum[]=new int[nums.length];
        int suffixsum[]=new int[nums.length];
         prefixsum[0]=0;
        for(int i=1;i<nums.length;i++){
            prefixsum[i]=prefixsum[i-1]+nums[i-1];
        }
       suffixsum[nums.length-1]=0;
       int n=nums.length;
       for(int i=n-2;i>=0;i--){
        suffixsum[i]=suffixsum[i+1]+nums[i+1];
       }
       int ans=-1;
       for(int i=0;i<nums.length;i++){
        if(prefixsum[i]==suffixsum[i]){
            ans=i;
            break;
        }
       }
       return ans;
    }
}
```

# Complexity Analysis

Time:O(n)

Space:O(n)

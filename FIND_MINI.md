# Find Mini

[Problem Link](https://leetcode.com/contest/weekly-contest-492/problems/minimum-capacity-box/submissions/1941489492/)


```
class Solution {
    public int minimumIndex(int[] arr, int k) {
      int ans=-1;
        for(int i=0;i<arr.length;i++){
            if(ans==-1 && k<=arr[i]){
                ans=i;
            }
            else if(k<=arr[i] && arr[ans]>arr[i]){
                ans=i;
            }
        }
        return ans;
    }
}
```

# Complexity Analysis

Time:O(n)

Space:O(1)

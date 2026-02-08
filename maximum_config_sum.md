# Maximum configuration sum

[Problem Link](https://www.geeksforgeeks.org/problems/max-sum-in-the-configuration/1)

```
class Solution {
    int maxSum(int[] arr) {
        // code here
        int sum_of_arr=0;
        int prev=0;
        for(int i=0;i<arr.length;i++){
            sum_of_arr+=arr[i];
            prev+=(i*arr[i]);
        }
        int n=arr.length;
        int ans=prev;
        for(int i=1;i<arr.length;i++){
            int temp=prev-(sum_of_arr-arr[i-1])+arr[i-1]*(n-1);
            ans=Math.max(ans,temp);
            prev=temp;
        }
        return ans;
    }
}
```
# Complexity Analysis

Time:O(n)

Space:O(1)

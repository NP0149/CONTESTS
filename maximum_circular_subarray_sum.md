# Maximum circular subarray sum

[Problem Link](https://www.geeksforgeeks.org/problems/max-circular-subarray-sum-1587115620/1)

```
class Solution {
    public int maxCircularSum(int arr[]) {
        // code here
        int total_sum=arr[0];
     int maxsum=arr[0];
     int minsum=arr[0];
     int currmaxsum=arr[0];
     int currminsum=arr[0];
        for(int i=1;i<arr.length;i++){
            currmaxsum=Math.max(currmaxsum+arr[i],arr[i]);
            maxsum=Math.max(maxsum,currmaxsum);
            
            currminsum=Math.min(currminsum+arr[i],arr[i]);
            minsum=Math.min(minsum,currminsum);
            total_sum+=arr[i];
        }
        if(maxsum<0){
            return maxsum;
        }
       
        return Math.max((total_sum-minsum),maxsum);
    }
}
```

# Complexity Analysis

Time:O(n)

Space:O(1)

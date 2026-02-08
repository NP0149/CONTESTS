# Last Moment before ant fall

[Problem Link](https://www.geeksforgeeks.org/problems/last-moment-before-all-ants-fall-out-of-a-plank/1)

```
class Solution {
    public int getLastMoment(int n, int left[], int right[]) {
        // code here
        int lastmoment=0;
        for(int pos:left){
            lastmoment=Math.max(lastmoment,pos);
        }
        for(int pos:right){
            lastmoment=Math.max(lastmoment,n-pos);
        }
        return lastmoment;
    }
}
```

# Complexity Analysis

Time:O(n)

Space:O(1)

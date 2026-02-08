# Dominant Indexes

[Problem Link](https://leetcode.com/problems/count-dominant-indices/)

```
class Solution {
    public int dominantIndices(int[] arr) {
        int rs[]=new int[arr.length];
      int n=arr.length;
     rs[n-1]=0;
     for(int i=n-2;i>=0;i--){
         rs[i]=rs[i+1]+arr[i+1];
     }
     for(int i=0;i<arr.length;i++){
         System.out.println(rs[i]);
     }
     System.out.println("hdcbx3dbcuj");
     int avg[]=new int[arr.length];
     int count=0;
     for(int i=0;i<arr.length-1;i++){
         avg[i]=rs[i]/(n-i-1);
        if(arr[i]>avg[i]){
            count++;
        }
     }
     System.out.println(count);
        return count;
    }
}
```

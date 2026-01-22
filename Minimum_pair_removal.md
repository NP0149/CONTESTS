# Minimum pair removal to make the array sorted

[Problem Link](https://leetcode.com/problems/minimum-pair-removal-to-sort-array-i/description/?envType=daily-question&envId=2026-01-22)


```
class Solution {
    static boolean issorted(List<Integer> li){
        for(int i=0;i<li.size()-1;i++){
           if(li.get(i)>li.get(i+1)){
            return false;
           }
        }
        return true;
    }
    public int minimumPairRemoval(int[] arr) {
       List<Integer> li=new ArrayList<>();
       if(arr.length==0){
        return 0;
       }
       for(int i=0;i<arr.length;i++){
      li.add(arr[i]);
       }
       int op=0;
       while(!issorted(li)){
        int minsum=Integer.MAX_VALUE;
        int indx=-1;
         for(int i=0;i<li.size()-1;i++){
            int sum=li.get(i)+li.get(i+1);
            if(minsum>sum){
               indx=i;
                minsum=sum;
            }
         }
         li.set(indx,minsum);
         li.remove(indx+1);
         op++;
       }
       return op;
    }
}
```
# Complexity Analysis

Time:O(n)

Space:O(n^2)

# Minimum Prefix

[Problem Link](https://leetcode.com/problems/minimum-prefix-removal-to-make-array-strictly-increasing/)

```
class Solution {
    static boolean issorted(int arr[]){
        for(int i=0;i<arr.length-1;i++){
            if(arr[i]>=arr[i+1]){
                return false;
            }
        }
        return true;
    }
    public int minimumPrefixLength(int[] arr) {
       if(issorted(arr)){
           return 0;
       }
        if(arr.length<=1){
            return 0;
        }
        if(arr[arr.length-1]<arr[arr.length-2]){
            return arr.length-1;
        }
        int count=0;
        Stack<Integer> st=new Stack<>();
         for(int i=arr.length-1;i>0;i--){
               if(!st.isEmpty() && st.peek()==arr[i] || !st.isEmpty() && st.peek()<arr[i]){
              break;
          }
          if(st.isEmpty()){
              st.push(arr[i]);
          }
          if(st.peek()>arr[i]){
              st.push(arr[i]);
          }
   }
    while(!st.isEmpty()){
        count++;
        st.pop();
    }
        return arr.length-count;
    }}
```
# Complexity Analysis

Time:O(n)

Space:O(n)

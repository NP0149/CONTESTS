# Rotate Non negative numbers 

[Problem Link](https://leetcode.com/problems/rotate-non-negative-elements/submissions/1896081801/)


```
class Solution {
    static void reverse(int arr[],int start,int end){
        int i=start;
        int j=end;
        while(i<j){
            int temp=arr[i];
            arr[i]=arr[j];
            arr[j]=temp;
            i++;
            j--;
        }
    }
    static int[] rotate(List<Integer> li,int k){
        int a[]=new int[li.size()];
        for(int i=0;i<li.size();i++){
            a[i]=li.get(i);
        }
        int n=a.length;
        k=k%n;
        reverse(a,0,k-1);
        reverse(a,k,n-1);
            reverse(a,0,n-1);
        return a;
    }
    public int[] rotateElements(int[] arr, int k) {
      List<Integer> li=new ArrayList<>();
      if(k==0){
        return arr;
      }
        for(int i=0;i<arr.length;i++){
            if(arr[i]>=0){
                li.add(arr[i]);
                  arr[i]=0;
            }
        }
        if(li.size()==0){
            return arr;
        }
        int a[]=rotate(li,k);
        int idx=0;
        for(int i=0;i<arr.length;i++){
            if(arr[i]==0){
                arr[i]=a[idx++];
            }
        }
        return arr;
    }
}
```

# Complexity Analysis

Time:O(n)

Space:O(n)

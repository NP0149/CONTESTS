# Minimize maximum pair sum

[Problem Link](https://leetcode.com/problems/minimize-maximum-pair-sum-in-array/description/?envType=daily-question&envId=2026-01-24)

```
class Solution {
    public int minPairSum(int[] arr) {
        Arrays.sort(arr);
      List<Integer> li=new ArrayList<>();
      int i=0;
      int j=arr.length-1;
      while(i<j){
        li.add(arr[i]+arr[j]);
        i++;
        j--;
      }
      Collections.sort(li);
      return li.get(li.size()-1);
    }
}
```
# Complexities

Time:O(nlog n)

Space:O(n)

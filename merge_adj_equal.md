# Merge adjacent equal elements

[Problem Link](https://leetcode.com/problems/merge-adjacent-equal-elements/description/)

```
class Solution {
    public List<Long> mergeAdjacent(int[] arr) {
     List<Long> li=new ArrayList<>();
        for(int i=0;i<arr.length;i++){
            long curr=(long)arr[i];
             while (!li.isEmpty() && li.get(li.size() - 1).equals(curr)) {
                curr += li.remove(li.size() - 1);
            }
            li.add(curr);
        }
       return li;
    }
}
```

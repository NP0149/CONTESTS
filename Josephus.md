# Josephus Problem or k jumps in a circular array game

[Problem Link](https://www.geeksforgeeks.org/problems/josephus-problem/1)

```
class Solution {
    public int josephus(int n, int k) {
        // code here
        List<Integer> li=new ArrayList<>();
        for(int i=1;i<=n;i++){
            li.add(i);
        }
        int idx=0;
        while(li.size()>1){
            idx=(idx+k-1)%li.size();
            li.remove(idx);
        }
        return li.get(0);
    }
}
```
# Complexity Analysis

Time:O(n)

Space:O(n)


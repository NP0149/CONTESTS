# To sort the whole String the minimum number of operations needed

[Problem Link](https://leetcode.com/contest/weekly-contest-492/problems/minimum-operations-to-sort-a-string/)

```
class Solution {
    class Pair{
        char ch;
        int indx;
        Pair(char ch,int indx){
          this.ch=ch;
            this.indx=indx;
        }
    }
    public int minOperations(String s) {
        Pair arr[]=new Pair[s.length()];
        for(int i=0;i<s.length();i++){
            arr[i]=new Pair(s.charAt(i),i);
        }
        Arrays.sort(arr,(a,b)->a.ch-b.ch);
        int swaps=0;
        boolean visited[]=new boolean[arr.length];
        for(int i=0;i<arr.length;i++){
            if(visited[i] || arr[i].indx==i){
                continue;
            }
            int cycles=0;
            int j=i;
            while(!visited[j]){
                visited[j]=true;
                j=arr[j].indx;
                cycles++;
            }
            if(cycles>0){
                swaps+=cycles-1;
            }
        }
        return swaps;
    }
}
```
# Complexity Analysis

Time:O(n)

Space:O(n)

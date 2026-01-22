# Minimum number of swaps to sort the array

```
class Solution {
    public long minimumReplacement(int[] arr) {
        int mat[][]=new int[arr.length][2];
        for(int i=0;i<arr.length;i++){
            mat[i][0]=arr[i];
            mat[i][1]=i;
        }
        Arrays.sort(mat,(a,b)->Integer.compare(a[0],b[0]));
        int swaps=0;
        boolean visited[]=new boolean[arr.length];
        for(int i=0;i<mat.length;i++){
            int cycles=0;
            int j=i;
            if(visited[i]==true || mat[i][1]==i){
                continue;
            }
            while(!visited[j]){
                visited[j]=true;
                j=mat[j][1];
                cycles++;
            }
            swaps+=cycles-1;
        }
        return swaps;
    }
}
```

# Complexity Analysis

Time:O(n)

Space:O(n^2)

# Minimum cost to convert from original to target

[Problm Link](https://leetcode.com/problems/minimum-cost-to-convert-string-i/?envType=daily-question&envId=2026-01-29)

```
class Solution {
    public long minimumCost(String source, String target, char[] original, char[] changed, int[] cost) {
        int n=26;
        long inf=(long)1e18;
        long mat[][]=new long[n][n];
        //created the matrix
        for(int i=0;i<n;i++){
            for(int j=0;j<n;j++){
              if(i==j){
                mat[i][j]=0;
              }
              else{
                mat[i][j]=inf;
              }
            }
        }
        //assiginig all the given original and changed values
        for(int i=0;i<original.length;i++){
            int u=original[i]-'a';
            int v=changed[i]-'a';
            mat[u][v]=Math.min(mat[u][v],cost[i]);
        }
        //applying floyd warshall
        for(int k=0;k<n;k++){
        for(int i=0;i<n;i++){
            for(int j=0;j<n;j++){
                    if(mat[i][k]+mat[k][j]<mat[i][j]){
                        mat[i][j]=mat[i][k]+mat[k][j];
                    }
                }
            }
        }
      long mincost=0;
      for(int i=0;i<source.length();i++){
        int u=source.charAt(i)-'a';
        int v=target.charAt(i)-'a';
        if(mat[u][v]==inf){
            return -1;
        }
        else{
            mincost+=mat[u][v];
        }
      }
        return mincost;
    }
}
```

# Digitorial Permutation

[Problem Link](https://leetcode.com/problems/check-digitorial-permutation/description/)


```
class Solution {
   static int find(int num,int dp[]){
    return num*dp[num-1];
   }
   static boolean check(long sum,int m){
       List<Integer> li=new ArrayList<>();
       while(sum!=0){
        li.add((int)sum%10);
        sum=sum/10;
       }
       Collections.sort(li);
       List<Integer> li1=new ArrayList<>();
       while(m!=0){
        li1.add(m%10);
        m=m/10;
       }
       Collections.sort(li1);
       if(li.size()!=li1.size()){
        return false;
       }
       for(int i=0;i<li.size();i++){
        if(li.get(i)!=li1.get(i)){
            return false;
        }
       }
       return true;
   }
    public boolean isDigitorialPermutation(int n) {
          int dp[]=new int[10];
          dp[0]=1;
     dp[1]=1;
     dp[2]=2;
     dp[3]=6;
     dp[4]=24;
     dp[5]=120;
     dp[6]=720;
      for(int i=7;i<10;i++){
          dp[i]=find(i,dp);
      }
      int m=n;
      long sum=0;
      while(n!=0){
        sum+=dp[n%10];
        n=n/10;
      }
       return check(sum,m);
    }
}
```
# Complexities

Time:O(n)

Space:O(n)

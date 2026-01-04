# Four divisors

[Problem Link](https://leetcode.com/problems/four-divisors/?envType=daily-question&envId=2026-01-04)

```
class Solution {
    static long find(int n){
        long sum=0;
        int count=0;
        for(int i=1;i*i<=n;i++){
            if(n%i==0){
                int d1=n/i;
                int d2=i;
                if(d1==d2){
                count++;
                sum+=d2;
                }
                else{
                 count=count+2;
                    sum+=d1;
                    sum+=d2;
                }
            }
            if(count>4) return 0;
        }
        if(count==4){
            return sum;
        }
        return 0;
    }
    public int sumFourDivisors(int[] arr) {
        long sum=0;
        for(int i=0;i<arr.length;i++){
            sum+=find(arr[i]);
        }
        return (int)sum;
    }
}
```
# Complexity Analysis

Time:O(m X sqrt(n))

Space:O(1)

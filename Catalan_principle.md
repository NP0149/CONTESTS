# Number of valid parenthesis

[Problem Link](https://www.geeksforgeeks.org/problems/valid-number-of-parenthesis/1)


```
class Solution {
    
    static long find_fact(int n){
        long prod=n;
        for(int i=n-1;i>0;i--){
            prod=prod*i;
        }
        return prod;
    }
    int findWays(int n) {
        int k=n/2;
        // code here
        if(n%2==1){
            return 0;
        }
        long fact_2k=find_fact(2*k);
        long fact_k1=find_fact(k+1);
        long fact_k=find_fact(k);
        long find=fact_2k/(fact_k1*fact_k);
        return (int)find;
    }
}

```
# Complexities

Time:O(n)

Space:O(1)

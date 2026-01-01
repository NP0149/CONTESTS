# Add one

[Problem Link](https://leetcode.com/problems/plus-one/submissions/1871282311/?envType=daily-question&envId=2026-01-01)

```
import java.math.BigInteger;
class Solution {
    public int[] plusOne(int[] arr) {
        BigInteger num=BigInteger.ZERO;
        for(int d:arr){
            num=num.multiply(BigInteger.TEN).add(BigInteger.valueOf(d));
        }
        num=num.add(BigInteger.ONE);
        String s=num.toString();
        int ans[]=new int[s.length()];
        for(int i=0;i<ans.length;i++){
            ans[i]=s.charAt(i)-'0';
        }
        return ans;
    }
}
```
# Compelxity Analysis

n is the length of number

Time:O(n)

Space:O(n)

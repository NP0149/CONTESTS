# count monobit numbers

[Problem Links](https://leetcode.com/problems/count-monobit-integers/)

```
class Solution {
    static int find(int n){
        String ans=Integer.toBinaryString(n);
        int count0=0;
        int count1=0;
        for(int i=0;i<ans.length();i++){
            if(ans.charAt(i)=='0'){
                count0++;
            }
            else{
                count1++;
            }
        }
        if(count1>0 && count0>0){
            return 0;
        }
        return 1;
    }
    public int countMonobit(int n) {
        int count=0;
        for(int i=0;i<=n;i++){
             count+=find(i);
        }
        return count;
    }
}
```

# Complexity Analysis

Time:O(n)

Space:O(1)

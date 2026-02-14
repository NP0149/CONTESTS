# Weighting word Mapping

[Problem Link](https://leetcode.com/contest/biweekly-contest-176/problems/weighted-word-mapping/description/)

```
class Solution {
    public String mapWordWeights(String[] words, int[] weights) {
           HashMap<Integer,Character> hm=new HashMap<>();
        
      for(int i=97;i<=122;i++){
          int val=i-97;
          hm.put(25-val,((char)i));
      }
        StringBuilder str=new StringBuilder();
     for(String s:words){
        int sum=0;
         for(int i=0;i<s.length();i++){
             sum+=weights[Math.abs('a'-s.charAt(i))];
         }
         int val=sum%26;
         str.append(hm.get(val));
     }
        return str.toString();
    }
}
```

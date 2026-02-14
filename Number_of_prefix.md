# Number of Prefix

[Problem Link](https://leetcode.com/contest/biweekly-contest-176/problems/number-of-prefix-connected-groups/)


```
class Solution {
    public int prefixConnected(String[] words, int k) {
        HashMap<String,Integer> hm=new HashMap<>();
        for(String s:words){
            StringBuilder sb=new StringBuilder();
            if(s.length() < k) continue; 
            for(int i=0;i<k;i++){
                
                sb.append(s.charAt(i));
            }
            hm.put(sb.toString(),hm.getOrDefault(sb.toString(),0)+1);
        }
        int count=0;
        for(String s:hm.keySet()){
            if(hm.get(s)>1){
                count++;
            }
        }
        return count;
    }
}
```

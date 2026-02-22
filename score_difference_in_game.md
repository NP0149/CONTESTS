# Score difference in a game

[Problem Link](https://leetcode.com/problems/find-the-score-difference-in-a-game/description/)

```
class Solution {
    public int scoreDifference(int[] arr) {
        int playera=1;
        int playerb=0;
        int playera_score=0;
        int playerb_score=0;
        for(int i=0;i<arr.length;i++){
            if(arr[i]%2==1){
                int temp=playera;
                playera=playerb;
                playerb=temp;
            }
            if((i+1)%6==0){
                 int temp=playera;
                playera=playerb;
                playerb=temp;
            }
            if(playera==1){
             playera_score+=arr[i];
            }
            else if(playerb==1){
                playerb_score+=arr[i];
            }
        }
        return playera_score-playerb_score;
    }
}
```

# Complexity Analysis

Time:O(n)

Space:O(1)

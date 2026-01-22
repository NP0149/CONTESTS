# Sum of subarray ranges

[Problem Link](https://www.geeksforgeeks.org/problems/sum-of-subarray-ranges/1)

# Brute force

```
class Solution {
    static int find(List<Integer> li){
        Collections.sort(li);
        return li.get(li.size()-1)-li.get(0);
    }
    public int subarrayRanges(int[] arr) {
        // code here
        int sum=0;
        for(int i=0;i<arr.length;i++){
            for(int j=i;j<arr.length;j++){
                List<Integer> li=new ArrayList<>();
                for(int k=i;k<=j;k++){
                    li.add(arr[k]);
                }
                sum+=find(li);
            }
        }
        return sum;
    }
}
```
# Complexity Analysis

Time:O(n^3)

Space:O(n^3)



# Better

```
class Solution {
    public int subarrayRanges(int[] arr) {
        // code here
        int sum=0;
        for(int i=0;i<arr.length;i++){
            int max=arr[i];
            int min=arr[i];
            for(int j=i;j<arr.length;j++){
                max=Math.max(max,arr[j]);
                min=Math.min(min,arr[j]);
                sum+=max-min;
            }
        }
        return sum;
    }
}
```

# Complexity Analysis

Time:O(n^2)

Space:O(1)

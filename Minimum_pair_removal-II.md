# Minimum Pair removal

[Problem Link](https://leetcode.com/problems/minimum-pair-removal-to-sort-array-ii/?envType=daily-question&envId=2026-01-23)

```
class Solution {
    public int minimumPairRemoval(int[] arr) {
        int n=arr.length;
        if(n<=1){
            return 0;
        }
        LinkedList<Long> li=new LinkedList<>();
        for(int i=0;i<arr.length;i++){
            li.add((long)arr[i]);
        }
        PriorityQueue<long[]> pq=new PriorityQueue<>(Comparator.comparingLong(a->a[0]));
        for(int i=0;i<li.size()-1;i++){
            pq.add(new long[]{li.get(i)+li.get(i+1),i});
        }
        int op=0;
        while(true){
            boolean sorted=true;
            Iterator<Long> it=li.iterator();
            long prev=it.next();
            while(it.hasNext()){
                long curr=it.next();
                if(prev>curr){
                    sorted=false;
                    break;
                }
                prev=curr;
            }
           if(sorted) break;
           long pair[]=pq.poll();
           int indx=(int)pair[1];
             if (indx >= li.size() - 1) continue;
           long sum=li.get(indx)+li.get(indx+1);
           li.set(indx,sum);
           li.remove(indx+1);
           if(indx-1>=0){
             pq.add(new long[]{li.get(indx-1)+li.get(indx),indx-1});
           }
           if(indx+1<li.size()){
            pq.add(new long[]{li.get(indx)+li.get(indx+1),indx});
           }
             op++;
        }
     return op;
    }
}
```

# Complexities

Time:O(n^2)

Space:O(n)

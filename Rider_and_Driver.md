# Rider and driver

[Problem Link](https://leetcode.com/problems/design-ride-sharing-system/description/)

```
class RideSharingSystem {
  public Deque<Integer> qdriver;
    public Deque<Integer> qrider;
    public RideSharingSystem() {
        qdriver=new ArrayDeque<>();
        qrider=new ArrayDeque<>();
    }
    
    public void addRider(int riderId) {
        qrider.addFirst(riderId);
    }
    
    public void addDriver(int driverId) {
        qdriver.addFirst(driverId);
    }
    
    public int[] matchDriverWithRider() {
        if(!qdriver.isEmpty() && !qrider.isEmpty()){
            return new int[]{qdriver.removeLast(),qrider.removeLast()};
        }
        return new int[]{-1,-1};
    }
    
    public void cancelRider(int riderId) {
        if(!qrider.isEmpty()){
            qrider.remove(riderId);
        }
    }
}

/**
 * Your RideSharingSystem object will be instantiated and called as such:
 * RideSharingSystem obj = new RideSharingSystem();
 * obj.addRider(riderId);
 * obj.addDriver(driverId);
 * int[] param_3 = obj.matchDriverWithRider();
 * obj.cancelRider(riderId);
 */
```
# Complexity Analysis

Time:O(n)

Space:O(1)

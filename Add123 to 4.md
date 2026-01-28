# Add123 to 4

## you will be given count of x number of pieces of papers ,y and z number of pieces of papers

```
import java.util.*;

class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int T = sc.nextInt();
        
        while (T-- > 0) {
            int X = sc.nextInt(); // count of 1s
            int Y = sc.nextInt(); // count of 2s
            int Z = sc.nextInt(); // count of 3s
            
            // Pair (1,3)
            int pair13 = Math.min(X, Z);
            
            // Pair (2,2)
            int pair22 = Y / 2;
            
            int totalPairs = pair13 + pair22;
            System.out.println(totalPairs);
        }
        
        sc.close();
    }
}
```
# Complexity Analysis

Time:O(1)

Space:O(1)

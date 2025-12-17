```
import java.util.*;

class Codechef {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();

        while (t-- > 0) {
            long n = sc.nextLong();
            long m = sc.nextLong();

            // Minimum possible sum
            if (m < n) {
                System.out.println("NO");
                continue;
            }

            long diff = m - n;

            // Check divisibility
            if (diff % 4 != 0) {
                System.out.println("NO");
                continue;
            }

            long b = diff / 4; // number of +5 moves

            if (b <= n) {
                System.out.println("YES");
            } else {
                System.out.println("NO");
            }
        }
    }
}

```

# Odd Operatiions

```
import java.util.*;

class Codechef {

    static int minOperations(long N) {

        // Case 0: Already odd
        if (N % 2 == 1) return 0;

        String s = Long.toString(N);
        boolean hasOddDigit = false;

        for (char c : s.toCharArray()) {
            int d = c - '0';
            if (d % 2 == 1) {
                hasOddDigit = true;
                break;
            }
        }

        // Case 1: Can reorder to make it odd
        if (hasOddDigit) return 1;

        // Case 2: Single digit even number -> impossible
        if (N < 10) return -1;

        // Case 3: All digits even, multi-digit number
        return 2;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int T = sc.nextInt();

        while (T-- > 0) {
            long N = sc.nextLong();
            System.out.println(minOperations(N));
        }
    }
}

```

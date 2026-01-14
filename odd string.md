# Odd String

[problem Link](https://www.codechef.com/START221D/problems/LMP2)

```
import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
    static String find(String s){
          int[] freq = new int[26];

        for (char c : s.toCharArray()) {
            freq[c - 'a']++;
            if (freq[c - 'a'] > 2) {
                return "NO";
            }
        }

        return "YES";

    }
	public static void main (String[] args) throws java.lang.Exception
	{
	    Scanner sc=new Scanner(System.in);
	int t=sc.nextInt();
  for(int i=0;i<t;i++){
      int n=sc.nextInt();
      String s=sc.next();
      System.out.println(find(s));
  }
	}
}

```

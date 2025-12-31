```
import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
	public static void main (String[] args) throws java.lang.Exception
	{
		Scanner sc=new Scanner(System.in);
		int n=sc.nextInt();
		int m=sc.nextInt();
	    int count=0;
	    while(n>0 && m>0){
	        if(m>=2 && n<m){
	            m=m-2;
	            n--;
	            count++;
	        }
	        else{
	            n--;
	            m=m-1;
	        }
	    }
	    System.out.println(count);
	}
}
```

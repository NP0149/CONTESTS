# Divisible by 2 or 5

[Problem LInk](https://www.codechef.com/START231D/problems/NO25PLS)

```
import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
    static int find_nearest(int n){
        if(n<2){
            return 2;
        }
        if(n%2==0){
            int m=n/2;
            return (m-1)*2;
        }
        return (n/2)*2;
    }
    static int find(int n){
        if(n%2==0 || n%5==0){
            if(n%2==0 && n%5==0){
                return 0;
            }
            else{
                return 1;
            }
        }
        else{
            return 0;
        }
    }
	public static void main (String[] args) throws java.lang.Exception
	{
	     Scanner sc=new Scanner(System.in);
	    int t=sc.nextInt();
	    for(int i=0;i<t;i++){
	 int n=sc.nextInt();
	 int k=find(n);
	 if(k==0){
	     System.out.println(Math.abs(n-find_nearest(n)));
	 }
	 else{
	     System.out.println(0);
	 }
	}
	}
}
```

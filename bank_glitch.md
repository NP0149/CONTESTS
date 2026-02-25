# Bank glitch

[Problem Link](https://www.codechef.com/START227D/problems/BANKGLITCH)


```
import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
	public static void main (String[] args) throws java.lang.Exception
	{
	 Scanner sc=new Scanner(System.in);
     int t=sc.nextInt();
     for(int i=0;i<t;i++){
         int a=sc.nextInt();
         int b=sc.nextInt();
         int x=sc.nextInt();
         int y=sc.nextInt();
         int money=0;
         if(a>=x){
         int times=a/x;
         
        money=(a-(times*x))+(b+(times*y));
         }
         else{
             money=a+b;
         }
         System.out.println(money);
     }
	}
}

```

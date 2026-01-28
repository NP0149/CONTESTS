# School Trip

[Problem Link](https://www.codechef.com/problems/SCHOOLTRIP)

```
import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
	public static void main (String[] args) throws java.lang.Exception
	{
		// your code goes here
		Scanner sc=new Scanner(System.in);
		int t=sc.nextInt();
		for(int i=0;i<t;i++){
		    int n=sc.nextInt();
		    int x=sc.nextInt();
		    int k=sc.nextInt();
		    int sub=x%k;
		    int add=k-sub;
		    if(add<sub && add<=n-x){
		        System.out.println(add);
		    }
		    else if(sub<add ){
		        System.out.println(sub);
		    }
		    else{
		        System.out.println(sub);
		    }
		}

	}
}

```

# Complexity Analysis

Time:O(1)

Space:O(1)

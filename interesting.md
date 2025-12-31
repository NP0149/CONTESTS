```
import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
    static int find_min(int arr[]){
        int n=arr.length;
        int x=0;
        for(int i=0;i<n-1;i++){
            x=arr[i]+2*arr[i+1];
            arr[i+1]=x;
        }
        return x;
    }
    static int find_max(int arr[]){
        int k=0;
        int n=arr.length;
        for(int i=n-2;i>=0;i--){
         k=arr[i]+2*arr[i+1];
         arr[i]=k;
        }
        return arr[0];
    }
	public static void main (String[] args) throws java.lang.Exception
	{
	    Scanner sc=new Scanner(System.in);
	int t=sc.nextInt();
	for(int i=0;i<t;i++){
	    int n=sc.nextInt();
	    int arr[]=new int[n];
	    for(int j=0;j<n;j++){
	        arr[j]=sc.nextInt();
	    }
	    int []b=arr.clone();
       System.out.println(find_min(arr));
       System.out.println(find_max(b));
	}

	}
}

```

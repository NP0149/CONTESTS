# wearing jacket

[Problem Link](https://www.codechef.com/START221D/problems/LMP2E)

```
import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
    static int find(int arr[],int a,int b){
       int count = 0;
        boolean wearing = false;

        for (int temp : arr) {

            if (temp < a) {
                if (!wearing) {
                    count++;
                    wearing = true;
                }
            } 
            else if (temp > b) {
                wearing = false;
            }
        }

        return count;
    }
	public static void main (String[] args) throws java.lang.Exception
	{
	 Scanner sc=new Scanner(System.in);
	 int t=sc.nextInt();
	 for(int i=0;i<t;i++){
	      int n=sc.nextInt();
	 int a=sc.nextInt();
	 int b=sc.nextInt();
	 int arr[]=new int[n];
	 for(int j=0;j<n;j++){
	     arr[j]=sc.nextInt();
	 }
	 System.out.println(find(arr,a,b));
	 }

	}
}

```

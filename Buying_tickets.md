# Buying tickets

[Problem Link](https://www.codechef.com/START227D/problems/BUYTICK)

```
import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
    static int find(int n,int k,int arr[],String s){
       int a[]=new int[s.length()];
       for(int i=0;i<a.length;i++){
           if(s.charAt(i)=='1'){
               a[i]=1;
           }
       }
       List<int[]> li=new ArrayList<>();
       for(int i=0;i<arr.length;i++){
           li.add(new int[]{a[i],arr[i]});
       }
    Collections.sort(li,(l,b)->Integer.compare(l[1],b[1]));
       int sum=0;
       for(int i=0;i<li.size();i++){
           if(n<k){
               return -1;
           }
           if(li.get(i)[0]==0 && k>0){
               sum+=li.get(i)[1];
               k--;
           }
       }
       if(k==0){
           return sum;
       }
       return -1;
    }
	public static void main (String[] args) throws java.lang.Exception
	{
    Scanner sc=new Scanner(System.in);
    int t=sc.nextInt();
    for(int i=0;i<t;i++){
        int n=sc.nextInt();
        int k=sc.nextInt();
        int arr[]=new int[n];
        for(int j=0;j<n;j++){
            arr[j]=sc.nextInt();
        }
        String s=sc.next();
        int cost=find(n,k,arr,s);
        System.out.println(cost);
    }
	}
}
```

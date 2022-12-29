# Maximizing-LCS
Maximizing LCS
Question Link : https://www.codechef.com/problems/MAXLCS?tab=statement

Solution

```cpp
/* package codechef; // don't place package name! */

import java.util.*;
import java.lang.*;
import java.io.*;

/* Name of the class has to be "Main" only if the class is public. */
class Codechef
{
	public static void main (String[] args) throws java.lang.Exception
	{
		// your code goes here
		Scanner sc = new Scanner(System.in);
		int t=sc.nextInt();
		StringBuilder op=new StringBuilder("");
		
		while(t-->0){
		    int n = sc.nextInt();
		    String s1 = sc.next();
		    String s2 = (new StringBuilder(s1)).reverse().toString();
		    int[][] dp = new int[n][n];
		    
		    for(int i=0;i<n;i++){
		        for(int j=0;j<n;j++){
		            if(s1.charAt(i)==s2.charAt(j)){
		                if(i-1>=0&&j-1>=0){
		                    dp[i][j]=dp[i-1][j-1]+1;
		                }
		                else{
		                    dp[i][j]=1;
		                }
		            }
		            else{
		                int max =0;
		                if(i-1>=0){
		                    max =Math.max(max,dp[i-1][j]);
		                }
		                if(j-1>=0){
		                    max =Math.max(max,dp[i][j-1]);
		                }
		                dp[i][j]=max;
		            }
		        }
		    }
		    
		    op.append(dp[n-1][n-1]/2+"\n");
		}
		
		System.out.print(op.toString());
		
	}
}


```

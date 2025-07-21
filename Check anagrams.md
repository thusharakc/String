Problem Description

You are given two lowercase strings A and B each of length N. Return 1 if they are anagrams to each other and 0 if not.

Note : Two strings A and B are called anagrams to each other if A can be formed after rearranging the letters of B.


Problem Constraints

1 <= N <= 105
A and B are lowercase strings

public class Solution {
    public int solve(String A, String B) {
        
        int n=A.length(),m=B.length();
        int[] freqA=new int[26];   //this we can use to store the freq of a to b letters
        int[] freqB=new int[26];
        if(n!=m){
            return 0;
        }else{
            int i=0;
            //ASCI value of a is 97
            while(i<n){
                freqA[A.charAt(i)-97]++;
                freqB[B.charAt(i)-97]++;
                i++;
            }

            for(int k=0;k<26;k++){
              if( freqA[k]!=freqB[k]){
                  return 0;
              }
            }
        }

         return 1;  
    }
}

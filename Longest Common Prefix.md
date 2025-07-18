Given the array of strings A, you need to find the longest string S, which is the prefix of ALL the strings in the array.


The longest common prefix for a pair of strings S1 and S2 is the longest string S which is the prefix of both S1 and S2.

Example: the longest common prefix of "abcdefgh" and "abcefgh" is "abc".

public class Solution {
    public String longestCommonPrefix(String[] A) {
        int totalstrings=A.length;
        if(totalstrings==1)
        {return A[0];}


         int lengthOfSmallestString=Integer.MAX_VALUE;
         for(int i=0;i<totalstrings;i++){
        lengthOfSmallestString=Math.min(lengthOfSmallestString,A[i].length());
                 }
                 //System.out.print(lengthOfSmallestString);
     
        for(int i=0;i<lengthOfSmallestString;i++){
            char ch=A[0].charAt(i);

            for(int k=1;k<A.length;k++){
                // System.out.print(A[k]); 
                if(A[k].charAt(i)!=ch){
                  
                    return A[0].substring(0,i);
                }
            }
        }

        return A[0].substring(0,lengthOfSmallestString);
}
}
    

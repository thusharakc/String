Problem Description

You are given a string A of size N.


Return the string A after reversing the string word by word.

NOTE:

A sequence of non-space characters constitutes a word.
Your reversed string should not contain leading or trailing spaces, even if it is present in the input string.
If there are multiple spaces between words, reduce them to a single space in the reversed string.

public class Solution {
    public String solve(String A) {
        int n=A.length();
        StringBuilder sb=new StringBuilder();

        int i=n-1;
        while(i>=0){

            while((i>=0) && A.charAt(i)==' '){
                i--;
            }
            //this i will have a character
            int end=i;
            while((i>=0) && A.charAt(i)!=' '){
                i--;

            }
            int start=i+1;

            if(end>=0){
                if(sb.length()!=0){
                    sb.append(' ');
                }
                sb.append(A.substring(start,end+1));
            }
            
        }
        return new String(sb);
    }
}

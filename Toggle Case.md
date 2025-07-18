Problem Description

You are given a character string A having length N, consisting of only lowercase and uppercase latin letters.

You have to toggle case of each character of string A. For e.g 'A' is changed to 'a', 'e' is changed to 'E', etc.

public class Solution {
    public String solve(String A) {
        char[] ans=new char[A.length()];
    for(int i=0;i<A.length();i++){
       if (A.charAt(i)>='A' && A.charAt(i)<='Z' ){
           ans[i]=(char)(A.charAt(i)+32);
       }else{
          ans[i]=(char)(A.charAt(i)-32); 
       }
        }
        return new String(ans);
    }
}

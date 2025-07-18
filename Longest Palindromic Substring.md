Problem Description

Given a string A of size N, find and return the longest palindromic substring in A.

Substring of string A is A[i...j] where 0 <= i <= j < len(A)

Palindrome string:
A string which reads the same backwards. More formally, A is palindrome if reverse(A) = A.

Incase of conflict, return the substring which occurs first ( with the least starting index).


public class Solution {
    public String longestPalindrome(String A) {
        int n=A.length(),ans=1;
        int start=0,end=0; 
        for(int i=0;i<n-1;i++){  //make this as centre and check left and right

        int[] oddLengthPalindrome=lengthofSubstring(A,i,i);
        if(oddLengthPalindrome[2]>ans){
            start=oddLengthPalindrome[0];
            end=oddLengthPalindrome[1];
            ans=oddLengthPalindrome[2];
        }
        int[] evenLengthPalindrome=lengthofSubstring(A,i,i+1);
       if(evenLengthPalindrome[2]>ans){
            start=evenLengthPalindrome[0];
            end=evenLengthPalindrome[1];
            ans=evenLengthPalindrome[2];
        }

        }

        
        return A.substring(start,end+1);
    }



    public int[] lengthofSubstring(String A,int start,int end){

        while( start>=0 && end<A.length() && A.charAt(start)==A.charAt(end) ){

            start--;end++;
        }
        int length= end-1-(start+1)+1;
        return new int[]{ start+1, end-1 , length};
    } 
}

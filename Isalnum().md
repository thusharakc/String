# String

You are given a function isalpha() consisting of a character array A.
Return 1 if all the characters of a character array are alphanumeric (a-z, A-Z, and 0-9) else, return 0.

public class Solution {
    public int solve(char[] A) {
        int n=A.length,count=0;
        for(int i=0;i<n;i++){
            char ch=A[i];
            if((ch>='A' && ch<='Z') || (ch>='a' && ch<='z') || (ch>='0' && ch<='9')){
                continue;
            }
            return 0;
        }
        return 1;
       
    }
}

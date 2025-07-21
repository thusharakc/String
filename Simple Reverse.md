Given a string A, you are asked to reverse the string and return the reversed string.


public class Solution {
    public String solve(String A) {
        int n=A.length();
        StringBuilder sb=new StringBuilder();
        for(int i=n-1;i>=0;i--){
            sb.append(A.charAt(i));
        }
       return  new String(sb);
    }
}

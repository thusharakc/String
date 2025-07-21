Given a binary string A. It is allowed to do at most one swap between any 0 and 1. Find and return the length of the longest consecutive 1’s that can be achieved.


public class Solution {
    public int solve(String A) {
        int n=A.length();
        int countOfOne=0;

        for(int i=0;i<n;i++){
            if(A.charAt(i)=='1'){
                countOfOne++;
            }
        }
        if(countOfOne==n){
            return n;
        }
        if(countOfOne==0){
            return 0;
        }

        
        int ans=Integer.MIN_VALUE;

        for(int i=0;i<n;i++){
         
             if(A.charAt(i)=='0'){
                 //we need to check left and right 1s
                 int left=i-1,right=i+1,leftOne=0,rightOne=0;
                 while(left>=0 && A.charAt(left)=='1' ){
                     leftOne++;
                     left--;
                 }
                 while(right<n && A.charAt(right)=='1'){
                     rightOne++;
                     right++;
                 }
                //to swap the 0 with 1 we need extra 1, so compare with totalOneCount
                 if(rightOne+leftOne < countOfOne){
                   ans=  Math.max(ans,rightOne+leftOne+1);
                 }else{
                     return countOfOne;
                 }
             }
          
        }
        return ans;

    }
       
}


#Search insert position
class Solution {
    public int searchInsert(int[] nums, int target) {
        int s=0;
        int e=nums.length-1;

        while(s<=e){
            int mid=(s+e)/2;

            if(nums[mid]==target){
                return mid;
            }
            if(nums[mid]>target){
                e=mid-1;
            }
            if(nums[mid]<target){
                s=mid+1;
            }
        }
        return s;
    }
}
#Palindrome Number
class Solution {
    public boolean isPalindrome(int x) {
        if(x<0){
            return false;
        }
        int org=x;
        int rev=0;

        while(x!=0){
            int dig= x%10;
            rev=rev*10+dig;
            x=x/10;
        }
        return org==rev;
    }
}
#Find Smallest Letter Greater Than Target
class Solution {
    public char nextGreatestLetter(char[] letters, char t) {
        int s=0;
        int e=letters.length-1;

        while(s<=e){
            int mid=(s+e)/2;
            if(letters[mid]>t){
                e=mid-1;
            }
            if(letters[mid]<=t){
                s=mid+1;
            }
        }

        if(s==letters.length){
            return letters[0];
        }else{
            return letters[s];
        }
    }
}
#Richest customer wealth
class Solution {
    public int maximumWealth(int[][] accounts) {
        int ans=0;
        for(int i=0;i<accounts.length;i++){
            int sum=0;
            for(int j=0;j<accounts[i].length;j++){
                sum= sum+accounts[i][j];
            }
            if(sum>ans){
                ans=sum;
            }
        }
        return ans;
    }
}

#Find numbers with even digits of number
class Solution {
    public int findNumbers(int[] nums) {
        int ans=even(nums);
        return ans;
    }
    int even(int[] nums){
        int count=0;
        for(int i=0;i<nums.length;i++){
            int len=(int)Math.log10(nums[i])+1;
            if(len%2==0){
                count++;
            }
        }
        return count;

    }
}

#Two sum
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for(int i=0;i<nums.length;i++){
            for(int j=i+1;j<nums.length;j++){
                if(nums[i]+nums[j]==target){
                    return new int[]{i,j};
                }

            }
        }
        return new int[]{};
    }
}
        

        
    


# Split array largest sum

class Solution {
    public int splitArray(int[] nums, int k) {
        int start=0;
        int end=0;

        for(int i=0;i<nums.length;i++){
            start=Math.max(start,nums[i]);
            end=end+nums[i];
        }

        while(start<end){
            int mid=(start+end)/2;

            int sum=0;
            int pieces=1;

            for(int num:nums){
              if(sum+num>mid){
                sum=num;
                pieces++;
              }else{
                sum=sum+num;

              }

            }

            if(pieces>k){
                start=mid+1;
            }else{
                end=mid;
            }

        }
        return start;
    }
}
# Search in Rotated Sorted Array II 
class Solution {
    public boolean search(int[] arr, int target) {
        int peak = findPeakElement(arr);


        int first= binary(arr,target,0,peak);
        boolean ans=false;
        if(first==-1){
        first = binary(arr,target,peak+1,arr.length-1);

        }
        if(first!=-1){
            ans=true;
        }else{
            ans=false;
        }
        return ans;
    }
    
     int findPeakElement(int[] arr) {
        int start=0;
        int mid=0;
        int end=arr.length-1;
        while(start<=end){
            mid=(start+end)/2;
            if(mid<end&&arr[mid]>arr[mid+1]){
                return mid;
            }
            if(mid>start&&arr[mid-1]>arr[mid]){
                return mid-1;
            }
            if(start<end&&arr[mid]==arr[start]&&arr[mid]==arr[end]){
                if(end>start&&arr[start]>arr[start+1]){
                    return start;
                }
                start++;
                if(start<end&&arr[end-1]>arr[end]){
                    return end-1;
                }
                end--;
            }

            else if (arr[start] < arr[mid] || (arr[start] == arr[mid] && arr[mid] > arr[end])) {
            start = mid + 1;
        } else {
            end = mid - 1;
        }
        }
        return arr.length-1;
        
        
    }   
    int binary(int[] arr,int tar,int s,int e){
        int start=s;
        int end=e;
        while(start<=end){
            int mid=(start+end)/2;
            if(arr[mid]==tar){
                return mid;

            }
            if(arr[mid]>tar){
                end=mid-1;
            }else if(arr[mid]<tar){
                start=mid+1;
            }
        }
        return -1;

    
}


}
# find closest person 
class Solution {
    public int findClosest(int x, int y, int z) {

        if(Math.abs(z-x)>Math.abs(z-y)){
            return 2;
        }else if(Math.abs(z-x)<Math.abs(z-y)){
                        return 1;

        }else{
            return 0;
        }
    }
}
# Build Array from Permutation
class Solution {
    public int[] buildArray(int[] nums) {
        int[] ans=new int[nums.length];
        for(int i=0;i<nums.length;i++){
            ans[i]=nums[nums[i]];
        }
        return ans;
    }
}
# divisible and non divisible sums difference
class Solution {
    public int differenceOfSums(int n, int m) {
        int num1=0;
        int num2=0;
        for(int i=1;i<=n;i++){
            if(i%m==0){
                num1=num1+i;
            }else{
                num2=num2+i;
            }
        }

        return num2-num1;

        
    }
}
# Search in Rotated Sorted Array
class Solution {
    public int search(int[] arr, int target) {
        int peak = findPeakElement(arr);


        int first= binary(arr,target,0,peak);
        if(first==-1){
        first = binary(arr,target,peak+1,arr.length-1);

        }
        return first;
    }
    
     int findPeakElement(int[] arr) {
        int start=0;
        int end=arr.length-1;
        while(start<=end){
            int mid=(start+end)/2;
            if(mid<end&&arr[mid]>arr[mid+1]){
                return mid;
            }
            if(mid>start&&arr[mid-1]>arr[mid]){
                return mid-1;
            }
            if(arr[start]>arr[mid]){
                end=mid-1;
            }else{
                start=mid+1;
            }
        }
        return -1;
        
        
    }   
    int binary(int[] arr,int tar,int s,int e){
        int start=s;
        int end=e;
        while(start<=end){
            int mid=(start+end)/2;
            if(arr[mid]==tar){
                return mid;

            }
            if(arr[mid]>tar){
                end=mid-1;
            }else if(arr[mid]<tar){
                start=mid+1;
            }
        }
        return -1;

    
}


}
# Find in Mountain array
 
class Solution {
    public int findInMountainArray(int target, MountainArray arr) {
        int peak = findPeakElement(arr);
        int first= binary(arr,target,0,peak);
        if(first==-1){
        first = decreasingbinary(arr,target,peak,arr.length()-1);

        }
        return first;
    }
    
     int findPeakElement(MountainArray arr) {
        int start=0;
        int end=arr.length()-1;
        while(start<end){
            int mid=(start+end)/2;
            if(arr.get(mid)>arr.get(mid+1)){
                end=mid;
            }else{
                start=mid+1;
            }
        }
        return start;
        
    }
     int binary(MountainArray arr,int tar,int s,int e){
        int start=s;
        int end=e;
        while(start<=end){
            int mid=(start+end)/2;
            if(arr.get(mid)>tar){
                end=mid-1;
            }else if(arr.get(mid)<tar){
                start=mid+1;
            }else{
                return mid;
            }
        }
        return -1;

    
}
int decreasingbinary(MountainArray arr,int tar,int s,int e){
        int start=s;
        int end=e;
        while(start<=end){
            int mid=(start+end)/2;
            if(arr.get(mid)>tar){
                start=mid+1;
            }else if(arr.get(mid)<tar){
                end=mid-1;
            }else{
                return mid;
            }
        }
        return -1;
}
}
# Find peak element
class Solution {
    public int findPeakElement(int[] arr) {
        int start=0;
        int end=arr.length-1;
        while(start<end){
            int mid=(start+end)/2;
            if(arr[mid]>arr[mid+1]){
                end=mid;
            }else{
                start=mid+1;
            }
        }
        return start;
        
    }
}
# Peak Index in a Mountain Array
class Solution {
    public int peakIndexInMountainArray(int[] arr) {

        int start=0;
        int end=arr.length-1;
        while(start<end){
            int mid=(start+end)/2;
            if(arr[mid]>arr[mid+1]){
                end=mid;
            }else{
                start=mid+1;
            }
        }
        return start;
        
    }
}
# Concatenation of Array
class Solution {
    public int[] getConcatenation(int[] nums) {
        int[] arr=new int[nums.length*2];
        for(int i=0;i<2;i++){
            for(int j=0;j<nums.length;j++){
                if(i==0){
                arr[j]=nums[j];

                }else{
                    arr[nums.length+j]=nums[j];
                }
        }
        
        }
        return arr;
    }
}
# Score of a string
class Solution {

    public int scoreOfString(String s) {
        int ans=0;
        int[] arr=new int[s.length()];
        for(int i=0;i<s.length();i++){
        char ss=s.charAt(i);
        arr[i]=ss;

        }
        for(int i=0;i<s.length()-1;i++){

                int val=arr[i]-arr[i+1];
                if(val<0){
                    val=val*(-1);
                }
                ans=ans+val;
             

        }
        return ans;
    }
}
# Length of an argument
var argumentsLength = function(...args) {
        return args.length;

    
};
# Roman to Integer
class Solution {
    public int romanToInt(String s) {
    int ans=0;
    for(int i=0;i<s.length();i++){
        char c=s.charAt(i);
        int val=value(c);
        if(i<s.length()-1 && value(s.charAt(i))<value(s.charAt(i+1))){
            ans=ans-val;

        }else{
        ans=ans+val;

        }
 
    }
        return ans;
   }
   int value(char c) {
    switch (c) {
        case 'I': return 1;
        case 'V': return 5;
        case 'X': return 10;
        case 'L': return 50;
        case 'C': return 100;
        case 'D': return 500;
        case 'M': return 1000;
        default: return 0;
    }
}
}
#Find First and Last Position of Element in Sorted Array - LeetCode
class Solution {
    public int[] searchRange(int[] nums, int target) {

        int[] ans={-1,-1};

        int start=searching(nums,target,true);
        int end=searching(nums,target,false);
        ans[0]=start;
        ans[1]=end;
        return ans;
        
        
    }
    int searching(int[]nums,int target,boolean start){

        int s=0;
        int e=nums.length-1;
        int singleans=-1;

        while(s<=e){
            int mid=(s+e)/2;
            if(nums[mid]==target){
                singleans=mid;
                if(start){
                    e=mid-1;

                }else{
                    s=mid+1;

                }

            }
            if(nums[mid]<target){
                s=mid+1;
            }
             if(nums[mid]>target){
                e=mid-1;
            }
        }
        return singleans;

        }
}
#Reverse integer
class Solution {
    public int reverse(int x) {
        int rev=0;
       
            while(x!=0){
                int dig=x%10;
                if (rev > Integer.MAX_VALUE/10 || rev < Integer.MIN_VALUE/10) {
                return 0; 
                 }
                rev=rev*10+dig;
                x=x/10;
            }
        
        return rev;
    }
}
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
        

        
    

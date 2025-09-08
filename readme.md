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
        

        
    

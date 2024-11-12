``` java

class Solution {
    public int search(int[] nums, int target) {
        return binary_search(nums,target,0,nums.length-1);
    }
    public static int binary_search(int[] nums, int target, int start,int end){
        if(start>end){
            return -1;  
        }
        int mid= start+(end-start)/2; 
        if(nums[mid] == target){
            return mid;
        }
        if(nums[start]<=nums[mid]){
            if((nums[start] <= target) && (target <= nums[mid])){
                return binary_search(nums,target,start,mid-1);
            }
            else{
                return binary_search(nums,target,mid+1,end);
            }
        }
        else{
            if((nums[mid] <= target) && (target <= nums[end])){
                return binary_search(nums,target,mid+1,end);
            }
            else{
                return binary_search(nums,target,start,mid-1);
            }
        }
        
    }
}
```
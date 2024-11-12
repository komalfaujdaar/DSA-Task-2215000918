``` java 

class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        int start = 0;
        int end = matrix.length-1;
        int mid = 0;
        while(start <= end){
            mid = (start+end)/2;
            if(matrix[mid][0] == target){
                return true;
            } else if(matrix[mid][0] < target){
                if(matrix[mid][matrix[mid].length-1] >= target){
                    break;
                }
                start = mid+1;
            } else if(matrix[mid][0] > target){
                if(matrix[mid][matrix[mid].length-1] <= target){
                    break;
                }
                end = mid-1;
            }
        }
        start = 0;
        end = matrix[mid].length-1;
        int mid2 = 0;
        while(start <= end){
            mid2 = (start+end)/2;
            if(matrix[mid][mid2] == target){
                return true;
            } else if(matrix[mid][mid2] < target){
                start = mid2+1;
            } else if(matrix[mid][mid2] > target){
                end = mid2-1;
            }
        }
        return false;
    }
}
```
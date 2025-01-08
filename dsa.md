Q.1 
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        index_map={}
        for index, number in enumerate(nums):
            difference = target - number
            if difference in index_map:
                return[index_map[difference],index]
            index_map[number]=index


Q.5
class Solution:
    def getSecondLargest(self, arr):
    largest = second_largest = -1
    for num in arr:
        if num > largest:
            second_largest = largest
            largest = num
        elif num > second_largest and num != largest:
            second_largest = num
    return second_largest 

Q.9
class Solution {
    public int searchInsert(int[] nums, int target) {
        int left = 0, right = nums.length - 1;
  
        while (left <= right) {
            int mid = (left + right) / 2;
            if (nums[mid] == target) {
                return mid;
            } else if (nums[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        
        return left;  
    }
}


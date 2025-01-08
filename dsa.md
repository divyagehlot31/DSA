Q.1 Two Sum

```python
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
```

Q.2 Find n unique integers sum up to zero

O(N)

```python
class Solution(object):
    def sumZero(self, n):
        """
        :type n: int
        :rtype: List[int]
        """
        ans=[]
        if n%2!=0:
            ans.append(0)
        for i in range(1,(n//2)+1):
                ans.append(i)
                ans.append(-i)
        return ans
        
```

Q.3 Maximum Subarray

```python
class Solution:
    def maxSubArray(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        maxSum = nums[0]
        currentSum = nums[0]

        for num in nums[1:]:
            
            currentSum = max(num, currentSum + num)
            # Update maxSum if currentSum is larger
            maxSum = max(maxSum, currentSum)

        return maxSum

```

Q.4 3Sum

Q.5  Second Largest

```python
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
```

Q.6 Longest valid Parentheses

Q.7 Middle of the linked list

```python
class Solution(object):
    def middleNode(self, head):
        """
        :type head: Optional[ListNode]
        :rtype: Optional[ListNode]
        """
        
        slow = head
        fast = head
        
        # Traverse the list
        while fast and fast.next:
            slow = slow.next        # Move slow pointer one step
            fast = fast.next.next   # Move fast pointer two steps
        
        # When fast reaches the end, slow will be at the middle
        return slow
        
```

Q.8 Search in rotated sorted array
Q.9 Search insert position 

```python
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

```

Q.10 Merge sorted array

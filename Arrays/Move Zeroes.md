## Move Zeroes

### Description
Given an array `nums`, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.

### Example:
```java
Input: [0,1,0,3,12]
Output: [1,3,12,0,0]
```

### Solution
```java
class Solution {
    private void swap(int i, int j, int[] nums) {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }

    public void moveZeroes(int[] nums) {
        if (nums.length <= 1) return;
        
        int i = 0, j = 0, n = nums.length;
        
        for (int slow = 0, current = 0; current < n; current++) {
            if (nums[current] != 0) {
                swap(slow++, current, nums);
            }
        }
    }
}
```
Time Complexity: O(n)

Space Complexity: O(1)

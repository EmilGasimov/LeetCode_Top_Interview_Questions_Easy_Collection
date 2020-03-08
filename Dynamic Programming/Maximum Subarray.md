## Maximum Subarray
Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

#### Example:

```java
Input: [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
```

### Solution [own]
```java
class Solution {
    public int maxSubArray(int[] nums) {
        if(nums == null || nums.length == 0) return 0;
        if(nums.length == 1) return nums[0];
        int sum = nums[0], max = nums[0];
        for(int i = 1; i < nums.length; i++) {
            if(sum > 0) {
                sum += nums[i];
            }
            else sum = nums[i];
            max = Math.max(sum, max);
        }
        return max;
    }
}
```

Time Complexity : O(n)

Space Complexity : O(1)


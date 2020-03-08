## Move Zeroes
Given an array `nums`, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.

#### Example:
```java
Input: [0,1,0,3,12]
Output: [1,3,12,0,0]
```

### Solution 
```java
class Solution {
    public void moveZeroes(int[] nums) {
        int pos = 0;
        for(int i = 0; i < nums.length; i++) {
            if(nums[i] != 0) {
                if(i != pos) {
                    nums[pos] = nums[i];
                    nums[i] = 0;
                }
                pos++;
            }
        }
    }
}
```

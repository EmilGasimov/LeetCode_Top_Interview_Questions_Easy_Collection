## Description
Given an array of integers, find if the array contains any duplicates.
Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

### Example:
```
Input: [1,2,3,1]
Output: true
```

### Solution (own)
```javascript
/**
 * @param {number[]} nums
 * @return {boolean}
 */
var containsDuplicate = function(nums) {
    return (new Set(nums).size != nums.length);
};
```

Time Complexity: O(n)

Space Complexity: O(n)

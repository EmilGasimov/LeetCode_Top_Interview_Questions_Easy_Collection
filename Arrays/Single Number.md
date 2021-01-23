## Single Number
Given a non-empty array of integers, every element appears twice except for one. Find that single one.

#### Follow-up:
Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

### Example:
```
Input: [2,2,1]
Output: 1
```
### Constraints:
- 1 <= nums.length <= 3 * 104
- -3 * 104 <= nums[i] <= 3 * 104
- Each element in the array appears twice except for one element which appears only once.

### Solution 
```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var singleNumber = function(nums) {
    let n = nums[0];
    for (let i = 1; i < nums.length; i++) {
        n ^= nums[i];
    }
    return n;
};
```

Time Complexity: O(n)

Space Complexity: O(1)

[All about XOR](https://accu.org/index.php/journals/1915)


![image](https://lh3.googleusercontent.com/uwxV-rJMhEYMtP0ARYzONcWpqCqyO-Kj_4CQK1I6WhqTiclYJeoAexu6oHIEZlLP42A8wYBayLhKEWEJFR6PC1VRSsn3mFwOjroFRR2lQwmnJiZbn_INBBp4aIGP67zByMLyNUkeGdoNu5xqb_mUV7cobDKZ1lhYLTtNWMgNhr9xUKep3N7NWMwKp__aubgbym25ukXBzL215soJxltn9pOtHH-inizj9ywOqnYUDnntI8ljMxHl2uabnnXY-NSyBXLSrQIM3VFQHtJigHjorhslWAgtmy84wZ46I0DL8bL8kgyQk7YJb-qZWfkyO2-ghPF6J4hwYp-wu05H6DRTvO5qoq8bwisgFeOR338GYa2FmYu9mYFEjLuFI4QJISVbhp5sGLhv3iTRlbW4M4muucgNE75Tw6aIYrOXbk-R6OW2WJDqyF-ncspT1OVaUm2LHpBZsAPhuVi4A3pnKKPaZ1uNAIrcYhynzsSi_PT6KxvmGpXMpNEpJrZpFXe7NHq9MmptoltlkgHsAjgGYfLFLpRUNgCuxcNoF0qlwwAXM5ahlnCa9wZUzBLVO12593c7_p0GxeMAsrtkYfRU4iSDklWTR2Hl7EIJSqIkVm8RXrwgtuQxODiSTJ9Dmlgp9oIcjr9LAfz9x0jvXL73dq7hpw4sbp9acmzeZFRsqw0mvwU6KkGCYWg4v2s=w741-h353-no)


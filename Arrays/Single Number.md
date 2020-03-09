## Single Number
Given a non-empty array of integers, every element appears twice except for one. Find that single one.

#### Note:
Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

#### Example 1:
```java
Input: [2,2,1]
Output: 1
```


### Solution 
```java
public class Solution {
    public int singleNumber(int[] nums) {
        int res = 0;
        for(int num : nums) {
            res ^= num;
        }
        return res;
    }
}
```

![image](https://photos.google.com/photo/AF1QipN9RVHRQ7S2AGF16jK53Oq2Q80YtsUH--O7REXJ)

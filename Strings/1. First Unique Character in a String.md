## First Unique Character in a String
### Description
Given a string, find the first non-repeating character in it and return its index. If it doesn't exist, return -1.

### Examples:
```
s = "leetcode"
return 0.

s = "loveleetcode"
return 2.
```

#### Note: You may assume the string contains only lowercase English letters.

### Solution (own)
```javascript
/**
 * @param {string} s
 * @return {number}
 */
var firstUniqChar = function(s) {
    for (let i = 0; i < s.length; i++) {
        if (!s.slice(0, i).includes(s[i]) && !s.slice(i + 1).includes(s[i])) {
            return i;
        }
    }
    
    return -1;
};
```

Time Complexity: O(n^2)

Space Complexity: O(1)

### Solution 2 (a technique worth remembering)
```java
public class Solution {
    public int firstUniqChar(String s) {
        int freq [] = new int[26];
        for(int i = 0; i < s.length(); i ++)
            freq [s.charAt(i) - 'a'] ++;
        for(int i = 0; i < s.length(); i ++)
            if(freq [s.charAt(i) - 'a'] == 1)
                return i;
        return -1;
    }
}
```

Time Complexity: O(n)

Space Complexity: O(1)

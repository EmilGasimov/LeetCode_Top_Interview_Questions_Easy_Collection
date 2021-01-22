## Intersection of Two Arrays II
### Description
Given two arrays, write a function to compute their intersection.

### Example
```
Input: nums1 = [1,2,2,1], nums2 = [2,2]
Output: [2,2]
```
### Note:

- Each element in the result should appear as many times as it shows in both arrays.
- The result can be in any order.

### Follow up:
- What if the given array is already sorted? How would you optimize your algorithm?
- What if nums1's size is small compared to nums2's size? Which algorithm is better?
- What if elements of nums2 are stored on disk, and the memory is limited such that you cannot load all elements into the memory at once?

### Solution
```java
class Solution {
    public int[] intersect(int[] nums1, int[] nums2) {
        HashMap<Integer, Integer> map1 = new HashMap();
        HashMap<Integer, Integer> map2 = new HashMap();
        for (int i = 0; i < nums1.length; i++) {
            map1.put(nums1[i], map1.getOrDefault(nums1[i], 0) + 1);
        }
        for (int i = 0; i < nums2.length; i++) {
            map2.put(nums2[i], map2.getOrDefault(nums2[i], 0) + 1);
        }
        ArrayList<Integer> list = new ArrayList();
        for (Integer key: map1.keySet()) {
            for (int i = 0; i < Math.min(map1.get(key), map2.getOrDefault(key, 0)); i++) {
                list.add(key);
            }
        }
        int[] array = new int[list.size()];
        for (int i = 0; i < list.size(); i++) {
            array[i] = list.get(i);
        }
        return array;
    }
}
```

Time Complexity: O(m + n)

Space Complexity: O(m + n)

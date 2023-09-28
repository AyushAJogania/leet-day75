# leet-day75

# Move Even and Odd Numbers to Separate Ends of an Array

This problem involves rearranging the elements of an integer array in such a way that all even numbers are moved to the beginning of the array, followed by all the odd numbers. This rearrangement should be performed in-place, and there are no specific requirements regarding the order of even and odd numbers, as long as they are separated.

## Problem Statement

Given an integer array `nums`, you need to rearrange its elements in-place so that all even integers appear at the beginning of the array, followed by all odd integers. There is no specific requirement for the order of even and odd numbers, as long as they are separated.

## Examples

**Input:**
```
nums = [3,1,2,4]
```

**Output:**
```
[2,4,3,1]
```

**Explanation:** The outputs `[4,2,3,1]`, `[2,4,1,3]`, and `[4,2,1,3]` would also be accepted.

**Input:**
```
nums = [0]
```

**Output:**
```
[0]
```

## Constraints

- `1 <= nums.length <= 5000`
- `0 <= nums[i] <= 5000`

## Approach

A common approach to solving this problem is to use a two-pointer technique. We can maintain two pointers, one starting from the beginning of the array (`left`) and the other starting from the end of the array (`right`). Then, we move these pointers towards each other while following these rules:

- If `nums[left]` is even, we increment `left`.
- If `nums[right]` is odd, we decrement `right`.
- If `nums[left]` is odd and `nums[right]` is even, we swap them and increment `left` and decrement `right`.

By following these rules, we can ensure that even numbers are moved to the beginning and odd numbers to the end. When `left` becomes greater than or equal to `right`, the rearrangement is complete.

## Implementation

```cpp
class Solution {
public:
    vector<int> sortArrayByParity(vector<int>& nums) {
        int left = 0, right = nums.size() - 1;
        
        while (left < right) {
            if (nums[left] % 2 == 0) {
                left++;
            } else if (nums[right] % 2 == 1) {
                right--;
            } else {
                swap(nums[left], nums[right]);
                left++;
                right--;
            }
        }
        
        return nums;
    }
};
```

## Complexity Analysis

The time complexity of this solution is O(n), where n is the length of the input array `nums`. This is because we iterate through the array once with the two-pointer technique. The space complexity is O(1) as we perform the rearrangement in-place without using any additional data structures.


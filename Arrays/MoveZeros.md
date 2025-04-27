# Problem: Move Zeroes
# Link: https://leetcode.com/problems/move-zeroes/

Given an integer array `nums`, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

> **Note:** You must do this **in-place** without making a copy of the array.

---

## Example 1:

- **Input:** `nums = [0,1,0,3,12]`
- **Output:** `[1,3,12,0,0]`

## Example 2:

- **Input:** `nums = [0]`
- **Output:** `[0]`

---

## Constraints:

- `1 <= nums.length <= 10⁴`
- `-2³¹ <= nums[i] <= 2³¹ - 1`

---

## Follow up:

Could you minimize the total number of operations done?

---

## Hints:

- **Hint 1:**  
  In-place means we should not be allocating any space for extra array. But we are allowed to modify the existing array. However, as a first step, try coming up with a solution that makes use of additional space. For this problem as well, first apply the idea discussed using an additional array and the in-place solution will pop up eventually.

- **Hint 2:**  
  A two-pointer approach could be helpful here. The idea would be to have one pointer for iterating the array and another pointer that just works on the non-zero elements of the array.


# Solution: Move Zeroes (with Explanation)

```javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var moveZeroes = function(nums) {
    // `pos` keeps track of the position where the next non-zero element should go
    let pos = 0;

    // First pass: Move all non-zero elements to the front
    for (let i = 0; i < nums.length; i++) {
        if (nums[i] !== 0) {
            // If the current element is non-zero,
            // place it at the 'pos' index
            nums[pos] = nums[i];
            // Move 'pos' one step ahead
            pos++;
        }
    }

    // Second pass: Fill the remaining positions with 0s
    for (let i = pos; i < nums.length; i++) {
        nums[i] = 0;
    }
};


# Dry Run Example: [0,1,0,3,12]

| Step | i (current index) | nums[i] | pos (non-zero pointer) | Array state         | Action                  |
|-----:|:-----------------:|:-------:|:----------------------:|:--------------------:|:------------------------|
|  1   |         0          |    0    |           0            | [0,1,0,3,12]         | 0 is zero → do nothing  |
|  2   |         1          |    1    |           0            | [1,1,0,3,12]         | Place 1 at pos 0; pos++ |
|  3   |         2          |    0    |           1            | [1,1,0,3,12]         | 0 is zero → do nothing  |
|  4   |         3          |    3    |           1            | [1,3,0,3,12]         | Place 3 at pos 1; pos++ |
|  5   |         4          |   12    |           2            | [1,3,12,3,12]        | Place 12 at pos 2; pos++ |

---

## After First Loop (Moving non-zeros):
- Array becomes: `[1,3,12,3,12]`
- `pos = 3`

---

## Second Loop (Filling with zeroes):

| Step | i (current index) | Array state         | Action             |
|-----:|:-----------------:|:-------------------:|:-------------------|
|  1   |         3          | [1,3,12,0,12]        | Set nums[3] = 0    |
|  2   |         4          | [1,3,12,0,0]         | Set nums[4] = 0    |

---

# Final Result:
`[1,3,12,0,0]`

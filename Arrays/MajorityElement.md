# 169. Majority Element
#Link: https://leetcode.com/problems/majority-element/description/
## 📖 Description
Given an array `nums` of size `n`, your task is to return the **majority element**.

The majority element is defined as the element that appears **more than** ⌊n / 2⌋ times.  
You may **assume** that the majority element **always exists** in the array.

---

## 💡 Hints
- Since the majority element appears more than n/2 times, it must occupy the middle position if the array is sorted.
- Can you achieve a solution in **linear time** and **O(1) space**?
- Think about using **counting** techniques or **clever strategies** like the **Boyer-Moore Voting Algorithm**.

---

## 🧩 Problem
```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var majorityElement = function(nums) {
    const counts = {}
    const majorityCounts = Math.floor(nums.length/2)
    for (const num of nums) {
        counts[num] = (counts[num] || 0) + 1;
        if (counts[num] > majorityCounts) {
            return num;
        }
    }
};
```

---

## 📝 Explanation

1. **Initialize a counts object** to keep track of the frequency of each number in the array.
2. **Calculate the majority count** needed, which is `Math.floor(nums.length / 2)`.
3. **Iterate over the array**:
   - For each number `num`, increase its count in the `counts` object.
   - After updating the count, check if it exceeds `majorityCounts`.
   - If it does, **immediately return** the number because we have found the majority element.
4. **Efficiency**:
   - **Time Complexity**: O(n), since we traverse the array only once.
   - **Space Complexity**: O(n), because we might store counts for each unique element.

---


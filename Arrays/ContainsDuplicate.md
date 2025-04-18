### Link: https://leetcode.com/problems/contains-duplicate/description/



### Problem: Contains Duplicate

Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is **distinct**.

---

#### Example 1:
**Input:**  
`nums = [1, 2, 3, 1]`  
**Output:**  
`true`  
**Explanation:**  
The element `1` occurs at the indices `0` and `3`.

---

#### Example 2:
**Input:**  
`nums = [1, 2, 3, 4]`  
**Output:**  
`false`  
**Explanation:**  
All elements are distinct.

---

#### Example 3:
**Input:**  
`nums = [1, 1, 1, 3, 3, 4, 3, 2, 4, 2]`  
**Output:**  
`true`

---

#### Constraints:
- `1 <= nums.length <= 10^5`  
- `-10^9 <= nums[i] <= 10^9`


### Recommended Time & Space Complexity

You should aim for a solution with **O(n)** time and **O(n)** space, where `n` is the size of the input array.

---

### Hints

#### Hint 1
A brute force solution would be to check every element against every other element in the array.  
This would be an **O(n²)** solution. Can you think of a better way?

#### Hint 2
Is there a way to check if an element is a duplicate without comparing it to every other element?  
Maybe there's a **data structure** that is useful here.

#### Hint 3
We can use a **hash data structure** like a **HashSet** or **HashMap** to store elements we've already seen.  
This will allow us to check if an element is a duplicate in **constant time**.


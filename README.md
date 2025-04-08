# 🧮 LeetCode 3396 - Minimum Number of Operations to Make Elements in Array Distinct

This repository contains the Python solution for the LeetCode problem [3396. Minimum Number of Operations to Make Elements in Array Distinct ](https://leetcode.com/problems/minimum-number-of-operations-to-make-elements-in-array-distinct/).

---

## 💡 Problem Description

You are given an integer array `nums`. You need to ensure that all elements in the array are **distinct**.

To do this, you may perform the following operation any number of times:

- Remove the first 3 elements from the array.
- If the array has fewer than 3 elements, remove all remaining elements.

> An empty array is also considered to have distinct elements.

### 🧠 Objective

Return the **minimum number of operations** needed to make all elements in the array distinct.

---

## 🔍 Examples

### Example 1
#### Input: nums = [1,2,3,4,2,3,3,5,7] 
#### Output: 2 
#### Explanation:

+ After removing the first 3 → [4,2,3,3,5,7]

+ After removing the next 3 → [3,5,7] → All elements are distinct.

### Example 2

#### Input: nums = [4,5,6,4,4] 
#### Output: 2 
#### Explanation:

+ After removing first 3 → [4,4]

+ After removing all remaining → [] → Empty array is distinct.

### Example 2

#### Input: nums = [6,7,8,9] 
#### Output: 0 
#### Explanation:

+ All elements are already distinct.


---

## 🧠 Approach

- Use a `while` loop to check if the array has duplicates.
- If duplicates exist, remove the first 3 elements and count the operation.
- Repeat until all elements are distinct (or array is empty).

---

## 🐍 Python Solution

```python
class Solution:
    def minimumOperations(self, nums):
        operations = 0

        while len(nums) != len(set(nums)):
            nums = nums[3:]  # Remove first 3 elements
            operations += 1

        return operations
```
## ✅ Constraints
+ 1 <= nums.length <= 100

+ 1 <= nums[i] <= 100

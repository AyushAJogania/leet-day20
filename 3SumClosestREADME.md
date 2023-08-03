# leet-day20

# LeetCode Problem: 3Sum Closest

## Problem Statement
Given an integer array `nums` of length `n` and an integer `target`, find three integers in `nums` such that the sum is closest to `target`. Return the sum of the three integers.

You may assume that each input would have exactly one solution.

## Example
### Input
```
nums = [-1, 2, 1, -4]
target = 1
```
### Output
```
2
```
Explanation: The sum that is closest to the target is `2`. (-1 + 2 + 1 = 2).

## Constraints
- 3 <= `nums.length` <= 500
- -1000 <= `nums[i]` <= 1000
- -104 <= `target` <= 104

## Approach and Solution
The problem requires finding three integers whose sum is closest to the target. One approach to solve this problem is to sort the array and then use the Two-Pointer technique.

1. Sort the input array `nums`.
2. Initialize variables `closestSum` and `minDiff` to keep track of the closest sum and the minimum difference from the target, respectively. Set `closestSum` to 0 and `minDiff` to `INT_MAX`.
3. Iterate through the array using a for loop, with the loop variable `i` ranging from 0 to `n - 2`.
4. For each `i`, use two pointers (`left` and `right`) initialized to `i + 1` and `n - 1`, respectively.
5. While `left` is less than `right`, calculate the current sum of the three integers (`nums[i] + nums[left] + nums[right]`) and the difference between the current sum and the target. Update `closestSum` and `minDiff` if the current difference is smaller than the minimum difference encountered so far.
6. Move the pointers accordingly. If the current sum is less than the target, move the `left` pointer to increase the sum. Otherwise, move the `right` pointer to decrease the sum.
7. Continue the loop until all possible combinations are checked.
8. After the loop, return `closestSum`, which represents the sum of the three integers that are closest to the target.

The time complexity of this solution is O(n^2), where n is the length of the input array `nums`. This is because the sorting step takes O(n log n) time, and the two-pointer approach takes O(n) time.


---
title: "Maximum Sum of Two Non Overlapping Subarrays"
date: 2023-03-09T19:18:05-08:00
draft: false
---
This problem is from LeetCode [1039.](https://leetcode.com/problems/maximum-sum-of-two-non-overlapping-subarrays/description/)

We are given two lengths of the two subarrays.
We have to find the max value of the sum of the two subarrays.
This looks like a complicate problem but it is simple.

First, we need a way to quickly calculate the sum of a subarray.
This can be done with "prefix sum" where we add the items in the array
cumulatively.
The two subarrays cannot be overlapping, so we need a way to guarantee
that they do not overlap. If they do not overlap, then one subarray must
be before or after the other subarray. If length of the first subarray
is L and the second M, we can find the indices of where the two subarrays
start and end. 

L = (i - M) - (i - M - L)
M = i - (i - m)

We first calcualte the max sum of L while keeping room for
M on the right, then calculate max Sum of M while keeping room for L on the
right. Then we we turn the max of these two.

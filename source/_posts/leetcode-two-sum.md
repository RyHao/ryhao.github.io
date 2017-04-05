---
title: LeetCode - Two Sum
date: 2017-01-04 00:08:38
desc: Given an array of integers, return indices of the two numbers such that they add up to a specific target.
categories: Programming
tags:
	- LeetCode
	- Array
	- Hash Table
---

# Two Sum

Given an array of integers, return indices of the two numbers such that they add up to a specific target.
You may assume that each input would have exactly one solution.

#### Example:

Given nums = `[2, 7, 11, 15]`, target = `9`,

Because `nums[0] + nums[1] = 2 + 7 = 9`, return `[0, 1]`.

<!-- more -->

#### First Time Solution:

	/**
	* @param {number[]} nums
	* @param {number} target
	* @return {number[]}
	*/
	var twoSum = function(nums, target) {
			var resultSet = new Set();
			nums.forEach((num, idx) => {
					for(var i = 0 ; i < nums.length ; i += 1) {
							if (idx !== i) {
									var _num = nums[i]   
									if ((num + _num) === target) {
											resultSet.add(idx)
											resultSet.add(i)
									}
							}
					}
			})
			return Array.from(resultSet)
	};

#### Final Solution:

	/**
	* @param {number[]} nums
	* @param {number} target
	* @return {number[]}
	*/
	var twoSum = function(nums, target) {
			var result = []
			var mapping = {}
			nums.some((num, idx) => {
					if (typeof mapping[target - num] !== 'undefined') {
							result.push(mapping[target - num], idx)
							return true
					}
					mapping[num] = idx
					return false
			})
			return result
	};

[Source code](https://github.com/RyHao/LeetCode/blob/master/src/twoSum.js "Source code")

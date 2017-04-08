---
title: LeetCode - Length Of Longest Substring
date: 2017-04-04 16:16:46
desc: Given a string, find the length of the longest substring without repeating characters.
categories: Programming
tags:
	- LeetCode
	- Two Pointers
	- Hash Table
	- String
---

# Longest Substring Without Repeating Characters

Given a string, find the length of the longest substring without repeating characters.

#### Example:

Given `abcabcbb`, the answer is `abc`, which the length is 3.

Given `bbbbb`, the answer is `b`, with the length of 1.

Given `pwwkew`, the answer is `wke`, with the length of 3. Note that the answer must be a substring, `pwke` is a subsequence and not a substring.

<!-- more -->

#### First Time Solution:

	/**
	* @param {string} s
	* @return {number}
	*/
	var lengthOfLongestSubstring = function(s) {
			if (!s.length) return 0;
			var start = 0;
			var maxLength = 0;
			var charMap = new Map();
			for (var i = 0 ; i < s.length ; i += 1) {
					var c = s[i];
					if (charMap.has(c) && start <= charMap.get(c)) {
							start = charMap.get(c) + 1;
					} else {
							maxLength = Math.max(maxLength, i - start + 1);
					}
					charMap.set(c, i);
			}
			return maxLength;
	};			

#### Final Solution:

	/**
	* @param {string} s
	* @return {number}
	*/
	var lengthOfLongestSubstring = function (s) {
		const map = {};
		var left = 0;

		return s.split('').reduce((max, v, i) => {
			left = map[v] >= left ? map[v] + 1 : left;
			map[v] = i;
			return Math.max(max, i - left + 1);
		}, 0);
	};

[Source code](https://github.com/RyHao/LeetCode/blob/master/JavaScript/src/lengthOfLongestSubstring.js "Source code")

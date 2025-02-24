---
tags:
  - Learning/DSA
  - Algorithm
  - Array
---
# About
- Common technique to solve [[Arrays and Strings]] problems.
- Uses **two integer** variables to move along an iterate
- usually named `left` and `right`

```
There are multiple ways to implement this method
```

## Move them from out to inside

```
ℹ Start the pointers at the edges of the input. Move them towards each other until they meet.
```

1. Start one point at the first index `0` and the other point at the last index `input.length - 1`
2. Use a while loop until the pointers are equal to each other
3. At each iteration move the pointers to each other. 
	1. Increase pointer left
	2. decrement pointer right
	3. do both
4. `Deciding which pointer to move, depents on the problem`

```python
function fn(arr):
	left = 0
	right = arr.length - 1

	while left < right :
		# Do some logig here depending on the probelm
		# Do some logic on how to move the pointers
```

- You will never have more then $O(n)$
	- Pointers start $n$ away from each other
	- in each iteration they move one step close

## Example

```
Example 1: Given a string `s`, return `true` if it is a palindrome, `false` otherwise.

A string is a palindrome if it reads the same forward as backward. That means, after reversing it, it is still the same string. For example: "abcdcba", or "racecar".
```

```cpp
bool checkIfPalindrom(string s){
	int left = 0;
	int right = s.size() - 1;

	while (left < right){
		if (s[left] != s[right]){
			return false;
		}
		left++;
		right--;
	}

	return true;
}
```


```
Example 2: Given a **sorted** array of unique integers and a target integer, return `true` if there exists a pair of numbers that sum to target, `false` otherwise. This problem is similar to [Two Sum](https://leetcode.com/problems/two-sum/). (In Two Sum, the input is not sorted).

For example, given `nums = [1, 2, 4, 6, 8, 9, 14, 15]` and `target = 13`, return true because `4 + 9 = 13`.
```

- Brute force way it $O(n^2)$
- With 2 Pointers we can optimise to $O(n)$

#### How to optimise
- Start with two pointer
- **Note list is sorted**
- $1 + 15 = 16$ 
- We need to lower the $16$
- Decrement the `right` pointer to lower the number
- $1 + 14 = 15$ 
- Still lower
- ....

```cpp
bool checkForTarget(vector<int>& nums, int target){
	int left = 0
	int right = nums.size() - 1;
	while (left < right) {
		int curr = nums[left] + nums[right]
		if (curr == target) return true;

		if (curr > target){
			right--;
		} else{
			left++;
		}
	}
	return false;
}
```


### Different way to use Two Pointers

```
Move along both inputs simulataneously until all elements have been checked
```

1. Create two pointers, one for each iterable. Each pointer starts at the first index
2. Use a while loop until one of the pointers reaches the end of its iterable
3. At each hiteration of the loop, move the pointers forward
4. Do some magic in the while loop

```python
function fn (arr1, arr2):
	i = j = 0
	while i < arr1.length and j < arr2.length:
		# Do some logic
		# Increment pointer (i,j)
	# Exaust all loops
	while i < arr1.length:
		i++

	while j < arr2.length:
		j++
```
$$O(n+m)$$


```
Example 3: Given two sorted integer arrays `arr1` and `arr2`, return a new array that combines both of them and is also sorted.
```

```c
vector<int> cobine(vector<int>& arr1, vector<int>& arr2){
	vector<int> ans;
	int i = 0, j = 0;
	while (i < arr1.size() && j < arr2.size()){
		if (arr1[i] < arr2[j]){
			ans.push_back(arr1[i])
			i++;
		} else{
			and.push_back(arr2[j]);
			j++;
		}
	}

	while (i < arr1.size()){
		ans.push_back(arr1[i]);
		i++;
	}
	while (j < arr2.size()){
		ans.push_back(arr2[j]);
		j++;
	}
}
```

```
Example 4: [392. Is Subsequence](https://leetcode.com/problems/is-subsequence/).

Given two strings `s` and `t`, return `true` if `s` is a subsequence of `t`, or `false` otherwise.

A subsequence of a string is a sequence of characters that can be obtained by deleting some (or none) of the characters from the original string, while maintaining the relative order of the remaining characters. For example, "ace" is a subsequence of "abcde" while "aec" is not.
```

```c++
bool isSubsequence (string s, string t){
	int i = 0, j = 0;
	while (i < s.size() && j < t.size()){
		if (s[i] == t[j]){
			i++;
		}
		j++;
	}

	return i == s.size();
}
```
---
tags:
  - Learning/DSA
  - Array
---
Sliding window is using [[Two points]]

### Subarray
- Is a contiguous section of the array
- Must be adjacent to each other in the original array
- Must be in the same order

#### Example
`[1, 2, 3, 4]`

- `[1]`, `[2]`, `[3]`, `[4]` -> all alone
- `[1, 2]`, `[2, 3]`, `[3, 4]` -> in 2er groupes
- `[1, 2, 3]`, `[2, 3, 4]` -> in 3er groupes
- `[1, 2, 3, 4]` -> all together
![[Pasted image 20241217171549.png | center | 600]]

## When to use Sliding window

- When finding out if a Subarray is "valid"
	- Constraint metric
	- Numeric restriction on the constraint

#### Example
Subarray is valid if it is less or equal to 10 `<= 10`
We need to find a constraint metric here

- Problem is asking for valid subarray

## The algorithm

- Subarray can be defined by **left bound** and **right bound** indexes
- we maintain `left` and `right` variable
- initial we have `left = right = 0`
- we _expend_ the size of the window by **incrementing** the `right` variable
- _removing_ elements is done by **incrementing** the `left` variable

```pseudocode
function fn(nums, k):
	left = 0
	curr = 0
	anser = 0
	
	for (int right = 0; right < nums.length; right++):
		curr += nums[right]
		
		while (curr > k);
			curr -= nums[left]
			left++
			
		answer = max(answer, right - left + 1)
	
	return answer
```
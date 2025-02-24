---
tags:
  - Algorithm
---
Prefix sum is summing the array by the previos value

### Example
| Input Number  | 1   | 2   | 3   | 4   | 5   | 6   | ... |
| ------------- | --- | --- | --- | --- | --- | --- | --- |
| Prefix Number | 1   | 3   | 6   | 10  | 15  | 21  |     |
- Prefix sum is there to keep count of each sub array


You can use the prefix sum to keep track of how many elments are there in a [[Sliding Window]] if you know this, you can handle the amount which is given there.

#### Example of average

k (position to look for) = `2`
window size = `2 * 2 + 1`
- To know how many there are before and after the index
example, we know ther are `15`
calculate the averfage `15/5 = 3`
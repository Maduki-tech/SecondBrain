---
tags:
  - Algorithm
  - sorting
---
$$O(n)$$

```go
func Insertion_sort(input []int) []int {
	n := len(input)

	for i := 1; i < n; i++ {
		key := input[i]
		j := i - 1

		for j >= 0 && input[j] > key {
			input[j+1] = input[j]
			j--
		}

		input[j+1] = key
	}

	return input
}
```

- Always look at the second element
- Compare this with the left element
- swap if needed
- Inner loop
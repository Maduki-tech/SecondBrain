---
tags:
  - Algorithm
  - sorting
---
## Time Complexity
$$O(n\log_n)$$

- Array wird in der hälfte geteilt und recursive aufgerufen, bis man nur noch ein element hat
- Merge function to iterate and merge the split elements together
	- 2 indexes at 0
	- loop over until one of the indexes in larger then the length
	- if left <= right 
		- add element to array
		- increate first index
	- else
		- add element to array
		- increase right index
- Clean up and add all remaining elements
```GO
func Merge_sort(input []int) []int {
	if len(input) <= 1 {
		return input
	} else {

		mid := len(input) / 2

		left := Merge_sort(input[:mid])
		right := Merge_sort(input[mid:])
		return merge(left, right)
	}

}

func merge(left []int, right []int) []int {
	result := []int{}
	i, j := 0, 0
	for i < len(left) && j < len(right) {

		if left[i] <= right[j] {
			result = append(result, left[i])
			i++
		} else {
			result = append(result, right[j])
			j++
		}
	}

	for i < len(left) {
		result = append(result, left[i])
		i++
	}
	for j < len(right) {
		result = append(result, right[j])
		j++
	}

	return result
}
```

## Anwendung
- Sortierung von großen datensätzen
- Externe Sortierung -> Daten zugroß um in den speicher zulesen
- Kann leicht manipuliert werden

## Vorteile
- Garantierte Leistung
- Einfach umsetzbar
- Parallel einsetzbar
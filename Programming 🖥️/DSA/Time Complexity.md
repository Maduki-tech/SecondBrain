---
tags:
  - Learning/DSA
---
```
ℹ Time the algorithm needs to run relative to the input size
```

### Example
- $O(n)$
- $O(n^2)$
- $O(2^n)$
- $O(log_{n})$
- $O(n * m)$

```
What is m? m can just be a new Variable (loop)
```

## Calculating Complexity
- We check the amount of loops we have
- If we have n (input) we can say $O(n)$ but if we have a Loop inside the function with fix iterations it is $O(1)$

### Rules
- **Ignore constants** -> $O(999999n)$ is still $O(n)$ 
- When we have multiple Inputs, we take in the most **powerful** one

## Analyzing 
```go
for (int num: arr){
	print(num)
}
```

- This is $O(n)$ (Loop)
- And $O(1)$ in the Print statement
- We take the most powerful -> $O(n)$

```go
for (int num: arr) {
    for (int i = 0; i < 500,000; i++) {
        print(num)
    }
}
```

- Outer Loop -> $O(n)$
- Inner Loop -> $O(500000)$ which is $O(1)$
- Complexity -> $O(n)$

```go
for (int num: arr) {
    for (int num2: arr) {
        print(num * num2)
    }
}
```

- We have to Loops which depend on each other
- Solution is $O(n²)$
- 
---
id: C Bitoperations
aliases: []
tags: []
---

# What does << and >> mean in C?

- It is some kind of Bit shifting

```c
#include <stdio.h>
int main() {
    int a = 3; // binary: 00000011
    int b = a << 1; // Left shift by 1: 00000110 (6 in decimal)
    int c = a >> 1; // Right shift by 1: 00000001 (1 in decimal)

    printf("a << 1 = %d\n", b);
    printf("a >> 1 = %d\n", c);

    return 0;
}
```

## What does & do?

> Logical bitwise *and*

### 🧑‍💼 How does it work

- `10101011` (byte)
- `00001111` (0x0F)
- `00001011` (result of bitwise AND)

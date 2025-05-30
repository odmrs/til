# variables_and_memory

---

In C, variables are **objects stored in RAM** (Random Access Memory). Each variable has:

- A **type** (`int`, `char`, `float`, etc.)
- An **address** in memory (its location)
- A **value** (the data it holds)

```c
int k; 
k = 2;  // lvalue = rvalue
```
- Declares an `int` variable
- Allocates memory
- Value is **garbage** (uninitialized)
- **lvalue**: expression referring to a memory location
- **rvalue**: value to be stored

More Example
```c
int j, k;
k = 2;
j = 7;
k = j;
```
In memory:
```c
[ j ] --> 7  
[ k ] --> 7
```
- `k = j;` copies the **value**, not the address

## 📚References & Resources
https://github.com/jflaherty/ptrtut13/blob/master/md/ch1x.md
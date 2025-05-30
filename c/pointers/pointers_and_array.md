# Pointers and Array

Why pointers need a type:
- The compiler needs to know the type to understand:
	- How many bytes to read/write at the pointer's location.
	- How much to move the pointer in memory with operations like `ptr++`.

Pointer arithmetic
- ptr + 1 doesn't add 1 byte - it adds ``sizeof(type)`` bytes.
	- Example: `int *ptr` -> ptr + 1 adds 4 bytes (assuming 4-bytes ints).

Arrays and pointers are closely related
- The name of an array (my_array) gives the address of its first element.
- You can assign it to a pointer: ptr = ``my_array;``.

Why arrays names are constants
- my_array is a label for a fixed memory location.
- You can't change where it points, so it's a constants pointer.

Void pointers (``void *``)
- A "Generic" pointer - can point to anything.
- Useful when you don't know or care about the data type yes.
- Common int funciotons like malloc() or genereric data structures.

How different indices in arrays work via a pointer arithmetic 

Memory layout of this: 

```c
int my_array[] = {1, 2, 3, 4};
```

If my_array[0] is at address 1000 (just an example), then:

| Index | Address | Value |
| ----- | ------- | ----- |
| 0     | 1000    | 1     |
| 1     | 1004    | 2     |
| 2     | 1008    | 3     |
| 3     | 1012    | 4     |
Each time you do `ptr++`, the pointer moves by 4 bytes. not 1 byte. This is because the type is int.

```c
ptr = my_array;
*(ptr * 2); // Gives value at my_array[2]. i.e, 3
```

That happen because first I add 4 bytes in the address of pointer, in this case the index 2. and after that show the value inside it i.e., 3.

my_array is the same as my_array[0], because:
- The array name gives the address of the first element. It's not a variable because you don't can move the address of this first element.

Why and how void * works
- Is a pointer to any data, like a generic type.
```c
void *vp;
int x = 5;

vp = x; // works
```
Is useful because:
- You can pass around memory address without caring about types.
- Used in:
	- malloc and free
	- Generic code like data structures or sorting algorithms.
Remember probably you will need to casting. and to cast you need to ``*(type *)vp``

## 📚References & Resources
https://github.com/jflaherty/ptrtut13/blob/master/md/ch2x.md
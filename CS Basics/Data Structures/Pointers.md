# Pointers

Pointers are variables that point to memory addresses.

Pointers allow you to read and manipulate data which is larger and more complex than a simple data type like *int* or *char*.

So, if you have a big chunk of data that you want passed around in your program, you can instead, just pass around the small pointer and not the big piece of data.

Pointers are used in linked lists:

```c
typedef struct _singeLink {
  char *value; // The * indicates that this is a pointer
  struct _singeLink *next; // recursively points to the next _singeLink as a pointer
} SINGLELINK;

SINGLELINK first;
first.value = 99;
first.next = NULL;

SINGLELINK *P;
```

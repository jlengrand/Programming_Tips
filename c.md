# C/C++

## Block keyboard interruptions (CTRL+C):

Include the signal header :
```C
#include signal.h
```

At the beginning of the main, insert

```C
signal(SIGINT, fction)
```

with

- **fction** the function to be started on detection.
- **SIGINT** the interrupt to be detected.


##Some simple basics that helped :

### About variables :

- age -> value
- &age -> pointer

### About pointers :

- ptr -> ptr value(which is an address)
- *ptr -> variable value placed in the address.

#### If age is a variable :

- age is its value
- &age is its pointer

If ptr is a pointer :

- ptr is the pointer value (which is an address)
- *ptr is the value of the variable contained in at the address.


## Pointers creation:

```C
int *ptr = NULL; //Is just a creation, the * does not stand for anything else than declaring the pointer.

int age = 10;

*ptr=&age; //ptr is already created, the * now means that whe want to assign its value
```

- Those two are equivalent (used for structures):

```C
a->b
*(a.b)
```
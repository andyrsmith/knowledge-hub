# Malloc

Malloc is used to allocate memory dynamically.  Use malloc when you will only know how much memory you need at runtime.

Malloc will return a pointer to the memory of NULL if memory request fails

example
```
uint8_t *color_arr = malloc(bitmap_size * sizeof(uint8_t));
```

In this example I am allocating a uint8_t (1 byte int) array which will store data however the size of the bitmap_size variable is.

Once allocated the memory should check for NULL, and if the the request comes back as NULL exit the program.  If contining with a NULL pointer then we might be accessing data that we didn't intend to.

## free

All memory allocated needs to be freed after we are done using it.  If not then there is a possiblity of a memory leak.

Example
```
free(color_arr);
```

Notes:
- All data must be free
- Only free memory that has been initialized with malloc
- Do not free memory more that once 

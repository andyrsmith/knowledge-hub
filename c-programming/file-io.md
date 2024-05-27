# File I/O

Binary and text files can be read.

## fopen

Using the function fopen we can are able to read or edit a file.

```
FILE file_pointer = fopen("name-of-file", "r")
```

fopen takes an argument of a string/ character array of the name of the file, and the second argument is the mode you wish to open file in.  This can be either read or write, but there are several different ways to read and write.

### Access Modes

| Mode | description |
| ---- | ----------- |
|  r   |  read text file |
|  w   | write text file |
|  rb  | read binary file |
| wb  | write binary file | 

TODO: add in other access modes


## fread

Once file is open fread function is used to store data from file and into a variable.

```
char image_type[2];

fread(&image_type, sizeof(image_type), 1, bitmap_file);
or
fread(&image_type, sizeof(char), 2, bitmap_file);
which is better?
```

fread takes in 4 agruments.  First is the variable in which we will store data, second is size of elements, third is number of elements, and the fourth and last is the variable of the file.

## fwrite

fwrite will write data to a file

It takes 4 agruments

- buffer: pointer to the object that will be written
- size: size of each object.  Can use sizeof to get size of object
- count: number of chunks to be written
- stream/file: where the data will be written to

Example

```
fwrite(&image_header, sizeof(image_type), 1, bitmap);
```
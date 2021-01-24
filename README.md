# Files for Assignment 1 - Fall 2020
You can compile the C++ code by running

```
make
```

# `dup.py` utility

Instead of storing really large files in your directory, and risking
running out of quota, you can use this `dup.py` to generate large
input to your program.

It is a simple python program that accepts a single argument "N". The argument  is a number of bytes to generate. `dup.py` reads in data from stdin, byte by byte, and outputs the data to stdout. It always outputs N bytes. If the data on stdin is bigger than N, only first N bytes are copied. If the data on stdin is shorten than N, the utility then repeats the data, until N bytes are generated.

Here is an example of how to feed 2GB of data to your program, generated
by repeating `t3.txt`:
```
$ ./dup.py 2000000000 < t3.txt | ./fast-pali
```
Here is how you can time your code on the same data:
```
$ ./dup.py 2000000000 < t3.txt | time ./fast-pali
```
Here is how to run strace in combination with `dup.py`:
```
$ ./dup.py 2000000000 < t3.txt | strace -c ./fast-pali
```


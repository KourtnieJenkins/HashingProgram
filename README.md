# HashingProgram
*Uses Java to implementat hashing techniques to store a set of values from a file.*

COP3530: Data Structures -- Assignment #6

**Assignment Overview:**
This program demonstrates hashing techniques such as Horner's polynomial, linear probing, and quadratic probing.

**Assignment Details:**
For this program you are going to read three files of strings (using only lowercase alpha chars, each with no blanks, and each
separated by a new line--all three files will be on the command line--build/run args). The data will be such as:

zyxabc
ace
bobbysue
maybeuptofortychars
etc

The files will have been constructed using Notepad on a Windows machine.

Each string should be thought of as a polynomial, such as

>'z'*26^5 + 'y'*26^4 + 'x'* 26^3 + 'a'*26^2 + 'b'*26^1 +'c'*26^0

>'a'*26^2 + 'c'*26^1 + 'e'*26^0

>etc

where 'z' is the ASCII int associated with it (similarly) for all alpha chars.
For example, 'a' ==97.

So each string is essentially treated as a very large int which causes overflow.
The strings might have as many as 40 chars so that the leading power would be 26**39.


Task 1: Count the number of strings in the first file, say n.
Task 2: Find the first prime number larger than 2n, say p (a hint for finding p is in the book).
Task 3: Construct an array A and another array B of size p (indexed from 0 to p-1) to hold strings.
Task 4: Insert each of the strings in the first file into A using linear probing and into B using 
        quadratic probing. In each case use Horner's polynomial.
        Print the contents of A (index, string, and probe length for each insertion, all three on a single  line) followed
        by the contents of B (index, string, and probe length) . Only do the printing for non-empty cells and 
        print the cells with the smallest index used first.
```
                                 A
                      index   string   probe length for insertion
                       3        xyz        4
                       etc
      ave probe length:                        x.xx           
                                 B
                      index   string   probe length for insertion
                       3        xyz        4
                       etc
                 ave:                     y.yy
```

It is required that you hash (Horner's polynomial) using the technique we discussed
in class so as to avoid overflow at each stage. See:
http://math.fullerton.edu/mathews/n2003/HornerMod.html and/or pages 564-565.


Task 5: Search for each of the strings in the second  file from  A using hashing and linear probing,
        and from B using hashing and quadratic probing. Print the following tables for A and B 
        (just for the searches) :
```
               String   Success Failure Probe length for success  Probe length for failure
                ...      yes                     ...
                ...              yes                                          ...
          
average probe length:                                  x.xx                         y.yy                     
```

Task 6: Delete each of the strings in the third file from  A (if present)  using hashing and linear probing,
        and from B (if present) using hashing and quadratic probing. Print the following tables for A and B
        (just for the deletions) :
```               
               String   Succcess Failure Probe length for success  Probe length for failure
                ...      yes                             ...
                ...              yes                                                ...
       
 average probe length:                                  x.xx                         y.yy


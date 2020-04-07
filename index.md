Dynamic arrays optimization

As a student at the SAE Institute of Geneva in the game programming section, I was tasked to implement and to optimize some of the basic features of a game engine. 

Here, I'll be presenting my work on DynArrays.

One problem with fixed-size arrays is that the programmer must assume a size for the array. This may lead to erroneous assumptions that can be the source of a lot of bugs. Because the maximum can be exceeded, directly causing bugs, and the array can be way bigger than needed, wasting memory.

Another problem is that the array is not expandable. Using a small size may be more efficient for the typical data, but prevents the program from running with larger data sets.

Both of these problems can be avoided by using a dynamically allocating an array of the right size.

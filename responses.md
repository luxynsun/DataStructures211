1. Using your BinarySearchTree implementation, run the provided RandomBSTBuilder program. This program builds a binary search tree by inserting random values into the tree and records the tree’s height in a file tree-heights.csv. Generate a plot of this output. How quickly does the height of a random BST seem to grow with its size? Is this growth what you expected? Why or why not?

Height seems to grow fast at first, as size grows. However, the growth of height slows down as size approaches infinity.
This shows logarithmic growth.
It fits my expectation, given O(h) for a binary search tree would be O(log n), and this rate of growth is logarithmic.

![Random BST](https://github.com/luxynsun/DataStructures211/blob/main/Picture1.png)

2. In Assignment 02, you wrote a program that counted the number of distinct words in a text file using a SimpleUSet implementation. Since words are stored as Strings—which implement the Comparable interface—the words can be stored in a SimpleSSet as well. Modify your word-reading program from Assignment 02 to compare the performance of your BinarySearchTree implementation to the provided ArraySimpleSSet implementation of SimpleSSet. Note that ArraySimpleSSet stores the words in an array, and uses binary search for all finding operations. Which implementation, BinarySearchTree or ArraySimpleSSet is faster for reading the words from a few provided texts? Is the difference significant? Why might you expect one or the other implementation to be faster?

ArraySimpleSSet proves to be faster, though the difference is not significant in seconds, it is more significant in nanoseconds. 
Please see several runs and their times in nanoseconds. TesterClass.java includes the program that will announce the resulting running time of a text file imported.
Text title/nanoseconds | BinarySearchTree | ArraySimpleSSet
-----------------------|------------------|----------------
The Ilad |7569 | 2032
English Words | 10351 | 2273
Moby Dick | 11620 | 2148
Portrait of the Artist | 16545 |2111

Possible reasons for binary search arrays to be slightly faster include:
1) A node in a binary search tree is bigger than an item in an array, for it needs to store left and right pointers and value.
2) To access a single value in the array only one read has to be done, for the tree we need two: the left or right pointer and the value.
3) How the two ADTs behave in cache and memory.  

# Pain vs. Suffering

## Big O Notation

     Big O notation is used in Computer Science to describe the performance or complexity of an algorithm

- O(1)

     `O(1)` describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set. 

- O(N)

     `O(N)` describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set. The example below also demonstrates how Big O favours the worst-case performance scenario; a matching string could be found during any iteration of the for loop and the function would return early, but Big O notation will always assume the upper limit where the algorithm will perform the maximum number of iterations.

- O(N²)

     `O(N²)` represents an algorithm whose performance is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set. Deeper nested iterations will result in O(N³), O(N⁴) etc.

- O(2^N)

     `O(2^N)` denotes an algorithm whose growth doubles with each addition to the input data set. The growth curve of an O(2^N) function is exponential
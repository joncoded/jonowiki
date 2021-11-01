# Efficiency (with big-O notation)

**Measuring efficiency** of algorithms: given an input size of n, what "pattern of time" would it take to process the algorithm if it operates in (constant, logarithmic, linear, quadratic, exponential and factorial) time?

| **Big-O notation** | **Time if n=10** | <p><strong>Time if</strong><br><strong>n=100</strong></p> | **Name**        | Example                                                                                                         |
| ------------------ | ---------------- | --------------------------------------------------------- | --------------- | --------------------------------------------------------------------------------------------------------------- |
| O(1)               | 1                | 1                                                         | **constant**    | instant hashtable lookup                                                                                        |
| O(log n)           | 1                | 10                                                        | **logarithmic** | binary tree search                                                                                              |
| O(n)               | 10               | 100                                                       | **linear**      | for loop                                                                                                        |
| O(n log n)         | 10               | 1,000                                                     | ?               | linear loop after a binary tree search (all inside another loop)                                                |
| O(n^2)             | 100              | 10,000                                                    | **quadratic**   | nested for loop                                                                                                 |
| O(2^n)             | 1,024            | 1.26 x 10^30                                              | **exponential** | Fibonacci                                                                                                       |
| O(n!)              | 3,628,800        | (too long!)                                               | **factorial**   | <p>find all permutations (!)</p><p>i.e. how many ways can you rearrange the letters of an n-letter word? n!</p> |

As we go down the list, notice how much more time it takes, as `n` gets large...

...thus, we aim to program using _efficient_ data structures when we have large amounts of input!

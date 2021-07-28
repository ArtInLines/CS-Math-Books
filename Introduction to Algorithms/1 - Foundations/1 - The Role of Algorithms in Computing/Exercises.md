!! Several exercises haven't been solved yet. Either because I didn't know how to solve them, or because I got bored of the task !!

# 1.1 Algorithms

## 1.1-1

### Give a real-world example that requires sorting or a real-world example that requires computing a convex hull.

-   Ranking Students after their grades
-   Putting books in the right order (i.e. alphabetically after author name)

## 1.1-2

### Other than speed, what other measures of efficiency might one use in a real-world setting?

-   Memory use
-   Bandwith use
-   Readability / How easy is it to understand and fix the program?
-   Security

## 1.1-3

### Select a data structure that you have seen previously, and discuss its strengths and limitations.

Array

-   Stores data points together in a specified order
-   Fixed size (both curse & blessing)
-   Takes O(n) to retrieve a data point from an Array of size n

## 1.1-4

### How are the shortest-path and traveling-salesman problems given above similar? How are they different?

Similar:

-   Both problems ask for shortest paths between nodes in a weighed graph

Different:

-   The travelling salesman isn't looking for the shortest path between two nodes, but the shortest path, that crosses all nodes.
-   The travelling salesman, as stated here, also has several trucks to achieve their goal, thus using several paths to come to a solution

## 1.1-5

### Come up with a real-world problem in which only the best solution will do. Then come up with one in which a solution that is “approximately” the best is good enough.

...

---

# 1.2 Algorithms as a technology

## 1.2-1

### Give an example of an application that requires algorithmic content at the application level, and discuss the function of the algorithms involved.

...

## 1.2-2

### Suppose we are comparing implementations of insertion sort and merge sort on the same machine. For inputs of size n, insertion sort runs in 8n$^2$ steps, while merge sort runs in 64n lg n steps. For which values of n does insertion sort beat merge sort?

```JavaScript
const insertionSortTime = (n) => 8 * n ** 2;
const mergeSortTime = (n) => 64 * n * Math.log2(n);

function smallestN() {
    let n = 2;
    // For n < 2, mergeSortTime(n) < 1
    // Values < 1 make no sense in this context, thus n >= 2;
    while (insertionSortTime(n) < mergeSortTime(n)) n++;
    return n;
}
```

The function produces 44, therefore we know that for values of `n < 44`, insertion sort is faster.
Note: Since non-integer values for n make no sense in this context, we can ignore them

## 1.2-3

### What is the smallest value of $n$ such that an algorithm whose running time is $100n^2$ runs faster than an algorithm whose running time is $2^n$ on the same machine?

```JavaScript
const quadraticTime = (n) => 100 * n ** 2;
const exponentialTime = (n) => 2 ** n;

function smallestN() {
    let n = 1;
    while (quadraticTime(n) >= exponentialTime(n)) n++;
    return n;
}
```

The function returns the solution `n = 15`;

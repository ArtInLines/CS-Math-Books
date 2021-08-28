# Definition

**Input:** A sequence of _n_ numbers $\{a _ { 1 }, a _ { 2 }, ..., a _ { n } \}$.

**Output:** A permuation (reordering) $\{a' _ { 1 }, a' _ { 2 }, ... a' _ { n }\}$ of the input sequence such that $a' _ { 1 } <= a' _ { 2 } <= ... <= a' _ { n }$.

# Algorithms

(in order of introduction in the book)

## Insertion Sort

### Explanation

> `Insertion Sort` is an efficient algorithm for sorting a small number of elements.
> Insertion sort works the way many people sort a hand of playing cards. We start with an empty left hand and the cards face down on the table. We then remove one card at a time from the table and insert it into the correct position in the left hand. To find the correct position for a card, we compare it with each of the cards already in the hand, from right to left, as illustrated in Figure 2.1. At all times, the cards held in the left hand are sorted, and these cards were originally the top cards of the pile on the table.

### Time Complexity

### Pseudocode

```
Insertion_Sort (A)
    for i = 1 to A.length
        key = A[i]
        // Insert A[i] into the sorted sequence A[1 ... i-1]
        j = i - 1
        while j >= 0 and A[j] > key
            A[j + 1] = A[j]
            j = j - 1
        A[j + 1] = key
```

### JavaScript

```JS
function insertionSort(A) {
    for (var i = 1; i < A.length; i++) {
        var key = A[i];
        var j = i - 1;
        while (j >= 0 && A[j] > key) {
            A[j + 1] = A[j];
            j--;
        };
        A[j + 1] = key;
    }
    return A;
}
```

## Selection Sort

### Explanation

1. Find the smallest element within A
2. Exchange the smallest element with the first element in A
3. Continue by doing the same for the sub-array A[i,...n] until the sub-array is of size 2 (A[n-1, n])

### Time Complexity

### Pseudocode

```
Selection_Sort (A)
    n = A.length
    for j = 0 to n-1
        smallest = j
        for i = j+1 to n
            if A[i] < A[smallest]
                smallest = i
        exchange A[j] with A[smallest]
```

### JavaScript

```JS
function selectionSort(A) {
    var n = A.length;
    for (j = 0; j < n - 1; j++) {
        var smallest = j;
        for (var i = j + 1; i < n; i++) if (A[i] < A[smallest]) smallest = i;
        swap(A, j, smallest)
    }
    return A
}

function swap(A, j, i) {
    var temp = A[j];
    A[j] = A[i];
    A[i] = temp
}
```

## Merge Sort

### Explanation

### Time Complexity

### Pseudocode

```
Merge_Sort (A, p, r)
    if p < r
        q = [(p + r) / 2]
        Merge_Sort(A, p, q)
        Merge_Sort(A, q+1, r)
        Merge(A, p, q, r)

Merge (A, p, q, r)
    n1 = q - p + 1
    n2 = r - q
    let L[1...n1 + 1] and R[1...n2 + 1] be new arrays
    for i = 1 to n1
        L[i] = A[q + j]
    for j = 1 to n2
        R[j] = A[q + j]
    L[n1 + 1] = Infinity
    R[n2 + 1] = Infinity
    i = 1
    j = 1
    for k = p to r
        if L[i] <= R[j]
            A[k] = L[i]
            i = i + 1
        else A[k] = R[j]
            j = j + 1
```

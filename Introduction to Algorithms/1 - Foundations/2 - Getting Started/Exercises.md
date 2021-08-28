# Insertion Sort

## 2.1-2

### Rewrite the INSERTION-SORT procedure to sort into nonincreasing instead of non-decreasing order.

```Pseudocode
for i = 1 to A.length
    key = A[i]
    // Insert A[i] into the sorted sequence A[1 ... i-1]
    j = i - 1
    while j >= 0 and A[j] < key
        A[j + 1] = A[j]
        j = j - 1
    A[j + 1] = key
```

## 2.1-3

### Consider the searching problem:

### **Input:** A sequence of n numbers A = {a1; a2; ... ;an} and a value v.

### **Output:** An index i such that v = A[i] or the special value NIL if v does not appear in A.

### Write pseudocode for linear search, which scans through the sequence, looking for v. Using a loop invariant, prove that your algorithm is correct. Make sure that your loop invariant fulfills the three necessary properties.

```
function (A, v)
    res = NIL
    for i = 0 to A.length
        if (A[i] == v) return i
    return res
```

**Loop Invariant:** The variable res, which is the return value of the function, is always the special value NIL or the index i such that v = A[i]

## 2.1-4

### Consider the problem of adding two n-bit binary integers, stored in two n-element arrays A and B. The sum of the two integers should be stored in binary form in an (n + 1)-element array C. State the problem formally and write pseudocode for adding the two integers.

**Input:** Two Arrays, A & B, representing Binary Numbers, each of size n, containing bits as elements.
**Output:** The Array C of size n+1, representing the sum of A & B.

```
function addBinaryArrays(A, B)
    C = Array of size n+1
    carry = 0
    for i = A.length-1 downto 0
        sum = A[i] + B[i] + carry
        if sum > 1
            sum = sum - 2
            carry = 1
        C[i + 1] = sum
    C[0] = carry
    return C
```

# Analyzing Algorithms

# Designing Algorithms

## 2.3-1

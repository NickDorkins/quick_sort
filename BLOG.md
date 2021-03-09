# Quick Sort

```
ALGORITHM 

QuickSort(arr, left, right)
    if left < right
        // Partition the array by setting the position of the pivot value 
        DEFINE position <-- Partition(arr, left, right)
        // Sort the left
        QuickSort(arr, left, position - 1)
        // Sort the right
        QuickSort(arr, position + 1, right)

ALGORITHM 

Partition(arr, left, right)
    // set a pivot value as a point of reference
    DEFINE pivot <-- arr[right]
    // create a variable to track the largest index of numbers lower than the defined pivot
    DEFINE low <-- left - 1
    for i <- left to right do
        if arr[i] <= pivot
            low++
            Swap(arr, i, low)

     // place the value of the pivot location in the middle.
     // all numbers smaller than the pivot are on the left, larger on the right. 
     Swap(arr, right, low + 1)
    // return the pivot index point
     return low + 1

ALGORITHM 

Swap(arr, i, low)
    DEFINE temp;
    temp <-- arr[i]
    arr[i] <-- arr[low]
    arr[low] <-- temp
```

> Note: The algorythm's are written in JavaScript and I will be referring to the contents in terms of python, i.e. `arr` in JavaScript = `list` in python.

## QuickSort():

The function QuickSort() starts off by being passed a `list` of values, along with a `left` value, and a `right` value.

```
QuickSort(arr, left, right)
```
We start off by checking to see if `left` is less than the `right` value

```
if left < right
```




| PASS | BEFORE | LEFT | RIGHT | 
| --- | --- | --- | --- |
| 1 | [8,4,23,42,16,15] | [8] | [15] | 
| 2 | [8,4,23,42,16,15] | [4] | [15] | 
| 3 | [8,4,23,42,16,15] | [23] | [15] | 
| 4 | [4,8,15,42,16,23] | [42] | [23] |
| 5 | [4,8,15,23,16,42] | [16] | [42] |
| 6 | [4,8,15,23,16,42] | [23] | [16] |
| Final Lists | [4,8,15,16,23,42]

> Remember that the passes iterate in each direction `left + 1` and the `right - 1`

```
       Left values index direction -->

                           list = [4,8,15,23,16,42]

                                                   <-- Right values index direction
```

<!-- Forgot the pivot value, add it into table -->
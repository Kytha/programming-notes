## Merge Sort

### Time Complexity

- Worst Case: O(n\*log n)
- Best Case: O(n\*log n)
- Average Case: O(n\*log n)

### Space Complexity

- Worst Case: O(n)

```python
# Merge two sorted partitions
def merge(arr, l, r, m, compare_func):
    # Make copies of each half. This is necessary because we are sorting in place.
    left_copy = arr[l:m + 1]
    right_copy = arr[m+1: r+1]

    i = 0
    j = 0
    # Set sorting index to lower bound
    sort_index = l

    # Traverse both partitions and merge together
    while i < len(left_copy) and j < len(right_copy):
        if compare_func(left_copy[i], right_copy[j]):
            arr[sort_index] = left_copy[i]
            i += 1
        else:
            arr[sort_index] = right_copy[j]
            j += 1
        sort_index += 1

    # Any left over items in the left or right half can then be added to the end of the partition, keeping in mind each half is already sorted
    while i < len(left_copy):
        arr[sort_index] = left_copy[i]
        i += 1
        sort_index += 1
    while j < len(right_copy):
        arr[sort_index] = right_copy[j]
        j += 1
        sort_index += 1


def merge_sort(arr, l, r, compare_func):
    # Base case; if partition length is 1 we stop
    if l >= r:
        return
    # Find center of partition. We use implicit operator "//" for integer
    m = (l + r) // 2

    # Recursively call merge_sort. This will divide each half into more halves until we reach our base case ^
    merge_sort(arr, l, m, compare_func)
    merge_sort(arr, m + 1, r, compare_func)

    # Merge and sort each half
    merge(arr, l, r, m, compare_func)
```

## Quick Sort

### Time Complexity

- Worst Case: O(n^2)
- Best Case: O(n\*log n)
- Average Case: O(n\*log n)

### Space Complexity

- Worst Case: O(log n)

```python
# Takes a sub-array, picks a pivot, then places that pivot in the correct location my swapping other elements around it
def partition(arr, l, r, compare_func):
    i = l
    j = r - 1

    # Chose last value as pivot
    pivot = arr[r]

    # Traverse sub-array and swap values to left and right of pivot based on result of compare_func
    while i <= j:
        while i <= j and compare_func(arr[j], pivot):
            j -= 1
        while i <= j and not compare_func(arr[i], pivot):
            i += 1
        if i <= j:
            arr[i], arr[j] = arr[j], arr[i]

    # Swap pivot value with value @ i. This is the correct pivot placement
    arr[r], arr[i] = arr[i], arr[r]

    return i


def quick_sort(arr, l, r, compare_func):
    # Base case: if sub-array length is 1 return
    if l >= r:
        return

    # Pivot the sub-array and get the final position of pivot. We will then split into smaller arrays on either side of pivot and recursively continue
    p = partition(arr, l, r, compare_func)
    quick_sort(arr, l, p-1, compare_func)
    quick_sort(arr, p+1, r, compare_func)
```

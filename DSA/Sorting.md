# Sorting Algorithms in Java

## What is Sorting?

Sorting is the process of arranging elements in ascending or descending order.

Example:

Before:

```text
8 4 2 9 1
```

After (Ascending):

```text
1 2 4 8 9
```

---

# Types of Sorting

### Comparison Based

- Bubble Sort
- Selection Sort
- Insertion Sort
- Merge Sort
- Quick Sort
- Heap Sort

### Non Comparison Based

- Counting Sort
- Radix Sort

---

# Bubble Sort

## Idea

Compare adjacent elements and swap them if they are in the wrong order.

## Algorithm

1. Compare adjacent elements.
2. Swap if left element is greater.
3. After every pass, the largest element reaches the end.
4. Repeat until the array is sorted.

## Java Implementation

```java
public static void bubbleSort(int[] arr) {

    int n = arr.length;

    for (int i = 0; i < n - 1; i++) {

        boolean swapped = false;

        for (int j = 0; j < n - i - 1; j++) {

            if (arr[j] > arr[j + 1]) {

                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;

                swapped = true;

            }

        }

        if (!swapped)
            break;

    }

}
```

---

# Selection Sort

## Idea

Find the smallest element and place it at the beginning.

## Algorithm

1. Find minimum element.
2. Swap with first unsorted element.
3. Repeat for remaining array.

## Java Implementation

```java
public static void selectionSort(int[] arr) {

    int n = arr.length;

    for (int i = 0; i < n - 1; i++) {

        int min = i;

        for (int j = i + 1; j < n; j++) {

            if (arr[j] < arr[min]) {

                min = j;

            }

        }

        int temp = arr[i];
        arr[i] = arr[min];
        arr[min] = temp;

    }

}
```

---

# Insertion Sort

## Idea

Insert each element into its correct position in the sorted part of the array.

## Algorithm

1. Assume first element is sorted.
2. Pick next element.
3. Shift larger elements to the right.
4. Insert at correct position.

## Java Implementation

```java
public static void insertionSort(int[] arr) {

    int n = arr.length;

    for (int i = 1; i < n; i++) {

        int key = arr[i];
        int j = i - 1;

        while (j >= 0 && arr[j] > key) {

            arr[j + 1] = arr[j];
            j--;

        }

        arr[j + 1] = key;

    }

}
```

---

# Merge Sort

## Idea

Uses Divide and Conquer.

1. Divide array into two halves.
2. Sort both halves.
3. Merge them.

## Java Implementation

```java
public static void mergeSort(int[] arr, int low, int high) {

    if (low >= high)
        return;

    int mid = (low + high) / 2;

    mergeSort(arr, low, mid);
    mergeSort(arr, mid + 1, high);

    merge(arr, low, mid, high);

}
```

---

# Quick Sort

## Idea

Choose a pivot and place it at its correct position.

Elements smaller than pivot go left.

Elements greater go right.

Repeat recursively.

## Java Implementation

```java
public static void quickSort(int[] arr, int low, int high) {

    if (low < high) {

        int pivot = partition(arr, low, high);

        quickSort(arr, low, pivot - 1);

        quickSort(arr, pivot + 1, high);

    }

}
```

---

# Heap Sort

## Idea

1. Build Max Heap.
2. Swap root with last element.
3. Heapify remaining elements.

## Java Implementation

```java
public static void heapSort(int[] arr) {

    int n = arr.length;

    for (int i = n / 2 - 1; i >= 0; i--)
        heapify(arr, n, i);

    for (int i = n - 1; i > 0; i--) {

        int temp = arr[0];
        arr[0] = arr[i];
        arr[i] = temp;

        heapify(arr, i, 0);

    }

}
```

---

# Counting Sort

## Idea

Count frequency of every element.

Place elements back according to their frequency.

Suitable for small integer ranges.

---

# Radix Sort

## Idea

Sort numbers digit by digit using Counting Sort.

Starts from the least significant digit.

---

# Sorting Comparison

| Algorithm | Best | Average | Worst | Space | Stable | In-place |
|-----------|------|----------|--------|--------|---------|-----------|
| Bubble    | O(n) | O(n²) | O(n²) | O(1) | ✅ | ✅ |
| Selection | O(n²) | O(n²) | O(n²) | O(1) | ❌ | ✅ |
| Insertion | O(n) | O(n²) | O(n²) | O(1) | ✅ | ✅ |
| Merge     | O(n log n) | O(n log n) | O(n log n) | O(n) | ✅ | ❌ |
| Quick     | O(n log n) | O(n log n) | O(n²) | O(log n) | ❌ | ✅ |
| Heap      | O(n log n) | O(n log n) | O(n log n) | O(1) | ❌ | ✅ |
| Counting  | O(n+k) | O(n+k) | O(n+k) | O(n+k) | ✅ | ❌ |
| Radix     | O(d(n+k)) | O(d(n+k)) | O(d(n+k)) | O(n+k) | ✅ | ❌ |

---

# Interview Questions

- Which sorting algorithm is the fastest?
- Which sorting algorithm is stable?
- Which sorting algorithm is in-place?
- Why is Merge Sort preferred for Linked Lists?
- Why is Quick Sort preferred for Arrays?
- Difference between Merge Sort and Quick Sort.
- Difference between Bubble, Selection, and Insertion Sort.

---

# Practice Problems

## Easy

- Sort an Array
- Merge Sorted Arrays
- Relative Sort Array

## Medium

- Sort Colors
- Kth Largest Element
- Top K Frequent Elements

## Hard

- Count Inversions
- Reverse Pairs
- Merge Intervals
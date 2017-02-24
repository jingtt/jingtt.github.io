---
layout: post
title: "Sorting Algorithms"
date: 2017-2-11
categories: CS
---



{:toc}



# Bubble Sort

- Time complexity: $O(n^2)$
- Space complexity: $O(n)$

```c++
vector<int> bubble_sort(vector<int>& a){
  for(int i = 0; i < a.size(); i++){
    for(int j = 0; j < a.size() - i; j++){
      if(a[j] < a[j+1]){
        int temp = a[j];
        a[j] = a[j+1];
        a[j+1] = temp;
      }
    }
  }
  return a;
}
```



```python
def bubble_sort(a):
    for i in range(len(a)):
        for j in range(len(a)-i):
            if a[j] < a[j+1]:
                a[j],a[j+1] = a[j+1],a[j]
    return a
```



# Quick Sort

- Worst-case: $O(n^2)$
- Average: $O(n\log n)$

Quick sort is a divide and conquer algorithm. It first divides a large array into two smaller sub-arrays. Pick an element called a pivot from the array. Reorder the array so that all elements with values less than the pivot come before the pivot, while all elements with values greater than the pivot come after it. Recursively apply the above steps.



```python
def quick_sort(a,left,right):
    if left >= right:
        return a
    pivot = a[right]
    low,high = left,right
    while left < right:
        while left < right and a[left] < pivot:
            left += 1
        a[left],a[right] = a[right],a[left]
        while left < right and a[right] > pivot:
            right -= 1
        a[left],a[right] = a[right],a[left]
    quick_sort(a,low,left-1)
    quick_sort(a,right+1,high)
    return a
```





# Merge Sort

Divide the unsorted list into n sublists, each containing 1 element. Repeatedly merge sublists to produce new.



## Top-down

```python
def merge_sort(a):
    if(len(a) <= 1): return a
    left = merge_sort(a[:len(a)/2])
    right = merge_sort(a[len(a)/2:])
    result = []
    while len(left) > 0 and len(right) > 0:
        if left[0] < right[0]:
            result.append(left.pop(0))
        else:
            result.append(right.pop(0))
    return result
            
```

## Bottom-up

```python
def merge(left,right):
    result = 0
    while len(left) > 0 and len(right) > 0:
        if left[0] < right[0]:
            result.append(left.pop(0))
        else:
            result.append(right.pop(0))
    
def merge_sort(a):
    if(len(a) <=1 ): return a
    timer = 1
    while(timer < len(a)):
        for i in range(0,len(a),timer):
            a[i:i+2*timer] = merge(a[i:i+timer],a[i+timer:i+2*timer])
        timer *= 2
    return a
        
                        
    
```





# Heap Sort





# Selection Sort

```python
def select_sort(a):
    for i in range(len(a)):
        for j in range(i,len(a)):
            if a[j] < a[i]:
                a[i],a[j] = a[j],a[i]
    return a
    
```



# Insertion Sort

```python
def insert_sort(a):
    for i in range(1,len(a)):
        key = a[i]
        for j in reversed(range(i)):
            if a[j] > key:
                a[j] = a[j+1]
            else:
                a[j+1] = key
    return a
                    
```



# Shell Sort

```python
def shell_sort(a,distance=2):
    
    for i in range():
        
    
    
```





# Count Sort



# Bucket Sort





# Radix Sort

```python
import math
def radix_sort(a):
    
```


---
layout: post
title: "Sorting Algorithms"
date: 2017-2-11
categories: CS
---



{:toc}



In general, there are eight common sorting algorithms.



# Bubble Sort



It repeatedly steps through the list to be sorted, compares each pair of adjacent items and swaps them if they are in the wrong order. The pass through the list is repeated until no swaps are needed, which indicates that the list is sorted.  



```c++
vector<int> a;
for(int i = 0; i < a.size(); i++){
  for(int j = 0; j < a.size() - i; j++){
    if(a[j]<a[j+1]){
      int temp = a[j];
      a[j] = a[j+1];
      a[j+1] = temp;
    }
  }
}
```



```python
a = []
for i in a:
    for 
```



# Quick Sort





# Merge Sort


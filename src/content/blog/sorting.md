---
title: "Algorithms part 4"
description: "Sorting"
pubDate: "Jan 15 2025"
heroImage: "/dimitry-b-S9T2A1dPRiY-unsplash.jpg"
---

# Sorting

Since the beginning of the computer era, we needed to use of sort mechanisms, we need to give order to things to figure out how we can organize things by it's properties, elements, quantity, amount, etc.

The general definition of sorting is:

Any `X[i]` is going to be less or equals `<=` to any `X[i + 1]`

one of the most basic algorithms and easy to visualize is bubble sort.

## Bubble sort

How bubble sort works, it will start from the first position and navigate through until the end of the array and what is going to do is: The next element to me, if I'm larger we swap positions. i.e.

```js
[1, 3, 7, 4, 2]

// first comparison
 x[i] = 1
 x[i + 1] = 3

 1 > 3 = false // validate that the element is greater in this case is smaller, then it skips

// next comparison
 x[i] = 7
 x[i + 1] = 4

 7 > 4 = true // in this case it is greater then swap

[1, 3, 4, 7, 2]

// next comparison
 x[i] = 7
 x[i + 1] = 2

 7 > 2 = true // in this case it is greater then swap

[1, 3, 4, 2, 7]

// After the first iteration the largest element goes to the end of the array.

[1, 3, 4, 2, 7]

// from here I am going to skip negative cases

 x[i] = 4
 x[i + 1] = 2

 7 > 2 = true // in this case it is greater then swap

[1, 3, 2, 4, 7]

 x[i] = 3
 x[i + 1] = 2

[1, 2, 3, 4, 7]

// The array is already ordered!
```

Let's do the actual implementation

```js
function bubbleSort(arr) {
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length - 1 - i; j++) {
      if (arr[j] > arr[j + 1]) {
        const temp = arr[j];
        arr[j] = arr[j + 1];
        arr[j + 1] = temp;
      }
    }
  }
}
```

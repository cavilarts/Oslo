---
title: "Search"
description: "This the part 2 of the algorithms series"
pubDate: "Jan 11 2025"
heroImage: "/janko-ferlic-sfL_QOnmy00-unsplash.jpg"
---

# Search

We will go through search algorithms and techniques. We will start from possibly the simplest one:

## Linear Search

Imagine that we have an array from `0` to `N` and we want to implement a function to search a given element from the array, we would like to represent the things as follow:

```
a = [...]
    0   N

search(a, v)
```

And we would like to implement the logic for this function, then we will start from the element 0 of the array and we will start asking
`a[0] == v` ? in if the element is the one that we are looking for, then awesome the element is at index 0, otherwise we will increment one index and validate if the item is the one that we are looking for `a[1] ==v`

## So what's the Big O of this type of approach?

As we mentioned on our (previous post)[https://carlos-website-sable.vercel.app/blog/algorithm-first.md/] we will take our worst case scenario:

Imagine that we have the array `[1, 2, 3, 4, 5, 6, 7, 8, 9]` and we are looking for the number `10` we are going to navigate all the way from index `0` to `N` and never find it so the amount of iterations if this case scenario will be proportional to the number of items that the array contains, therefor it will be `O(N)`

now lets implement this

## Implementation

```ts
function linearSearch(haystack: number[], needle: number): boolean {
  for (let i = 0; i < haystack.length; i++) {
    if (haystack[i] === needle) {
      return true;
    }
  }

  return false;
}
```

This is a really basic implementation (Note that I am using types to make it clearer). So in this implementation we are creating a function that takes an array and one value and search one by one through it, if it exist, then return true otherwise it simply return false.

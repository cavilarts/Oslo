---
title: "Binary Search"
description: "This the part 3 of the algorithms series"
pubDate: "Jan 13 2025"
heroImage: "/markus-spiske-JT1AI1nKWhg-unsplash.jpg"
---

# Binary Search

Binary search is the most common efficient search algorithm, it works with a sorted array and it divides repeatedly into two halves one greater and one smaller than the element to search.

Think in this problem in the following way, you and a friend are playing a game to guess a number from 1 to 10, your first attempt will be to go for each number until you get the right one, but there are also another approaches. You can choose a random element for each time which can be also a linear search (in some way) or you can follow the binary search approach

1 - divide the problem by 2 in this case choose the number five
2 - check if the number is greater, equal or smaller
3 - depending on the outcome of step 2 you can either
3.1 - if it is equal you have won, then finish
3.2 - if it is smaller, discard the portion that have numbers greater than our guess
3.3 - if it is bigger, discard the portion that have values smaller than our guess
4 - repeat the process

based on the steps above our implementation should look like

```ts
function binarySearch(haystack: number[], needle): boolean {
  let low = 0;
  let high = haystack.length;

  do {
    const middle = Math.floor(low + (high - low) / 2);
    const guess = haystack[middle];

    if (guess === needle) {
      return true;
    } else if (guess > needle) {
      high = m;
    } else {
      low = m + 1;
    }
  } while (low < high);

  return false;
}
```

as we can see here, we divide the problem by 2 with each iteration therefore our time complexity will be `O(log n)` and the space complexity will be `O(1)` since only few variables are needed for this implementation.

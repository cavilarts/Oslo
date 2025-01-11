---
title: "Algorithms part 1"
description: "This is an algorithms course"
pubDate: "Jan 10 2025"
# heroImage: '/blog-placeholder-3.jpg'
---

# Big O Time Complexity

Big O is a way to categorize your algorithms time or memory requirements based on input. It is not meant to be an exact measurement. It will not tell you how many CPU cycles it takes, instead it is meant to generalize the growth of your algorithm.

## Why do we use it?

Often it help us to make decisions about what data structures and algorithms to use. Knowing how they will perform can greatly help create the best possible program out there.

So let's do an small example

```js
function sum_char_codes(n: string): number {
  let sum = 0;

  for (let i = 0; i < n.lenth; i++) {
    sum += n.charCodeAt(i);
  }

  return sum;
}
```

It is not so obvious but if you look closely we receive `n` which is an string and based on the size of `n` if it increase the computation it is going to be more expensive.

But to make it simple for calculating the `Big O` of an algorithm we look for loops. In the example above there are just one look so it will be `O(N)` meaning that the computing complexity is linear.

But what about this:

```js
function sum_char_codes(n: string): number {
  let sum = 0;

  for (let i = 0; i < n.lenth; i++) {
    sum += n.charCodeAt(i);
  }

  for (let i = 0; i < n.lenth; i++) {
    sum += n.charCodeAt(i);
  }

  return sum;
}
```

In this case it will be `O(2N)`?

The answer is no, there are the following important concepts for this type of cases:

1 - Growth is with respect to the input
2 - Constants are dropped

Therefore `O(2N)` can be simplified to `O(N)` and this makes sense. That is because Big is meant to describe the upper bound of the algorithm. The constant eventually becomes irrelevant.

## Note

### There is practical vs theoretical differences

Just because `N` is faster than `N^2`, does not mean practically is always faster for smaller input.

Let's see another example

```js
function sun_char_codes(n: string) {
  let sum = 0;

  for (let i = 0; i < n.length; i++) {
    const charCode = n.charCodeAt(i);

    if (charCode == 69) {
      // Capital E
      return sum;
    }

    sum += charCode;
  }

  return sum;
}
```

What will be the complexity of this function?

It will be `O(N)` this is because we always take the worst case scenario. Therefore any string with `E` in it will terminate early unless E is the last item in the list in which case it is still `O(N)`.

This series continues with [Search](https://carlos-website-sable.vercel.app/blog/search)

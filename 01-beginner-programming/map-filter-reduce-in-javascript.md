---
title: "Understanding map(), filter(), and reduce() in JavaScript"
description: "Learn how map(), filter(), and reduce() transform arrays in JavaScript with practical examples."
category: "Beginner Programming"
audience: "Beginner developers"
difficulty: "Beginner"
---
# Understanding map(), filter(), and reduce() in JavaScript

Most JavaScript apps spend a lot of time reshaping lists: products from an API, users from a database, search results, cart items, form fields, and navigation links. `map()`, `filter()`, and `reduce()` are three array methods you will reach for constantly when working with that kind of data.

## Prerequisites

- Basic JavaScript variables and functions
- A working understanding of arrays from [What Is JavaScript?](what-is-javascript-and-how-does-it-work.md)
- Node.js or a browser console for practice

## What Are Array Methods?

An array method is a function available on an array value. `map()` creates a new array by transforming each item. `filter()` creates a new array by keeping only items that pass a condition. `reduce()` combines all items into one result, such as a total, object, or grouped value.

## When to Use Each Method

Use `map()` when every item should become something else. Use `filter()` when some items should stay and others should be removed. Use `reduce()` when the whole array should become one value, such as a total, lookup object, or grouped result.

## How It Works

All three methods return a new value instead of changing the original array. Each method receives a callback function. The callback runs once for each item and returns a value that means something different depending on the method.

| Method | Use it to | Callback should return |
| --- | --- | --- |
| `map()` | Transform each item | The new item |
| `filter()` | Keep matching items | `true` to keep, `false` to remove |
| `reduce()` | Build one final result | The next accumulator value |

## Example

This example starts with a list of products and prepares values for a shopping cart summary.

```javascript
const products = [
  { name: "Notebook", price: 12, inStock: true },
  { name: "Pen", price: 2, inStock: true },
  { name: "Desk lamp", price: 30, inStock: false },
];

const availableProducts = products.filter((product) => product.inStock);
const productNames = availableProducts.map((product) => product.name);
const totalPrice = availableProducts.reduce((total, product) => {
  return total + product.price;
}, 0);

console.log(productNames); // ["Notebook", "Pen"]
console.log(totalPrice); // 14
```

`filter()` keeps only products in stock. `map()` extracts the product names. `reduce()` starts at `0` and adds each available product price to the running total.

## Common Mistakes

- Using `map()` when you only need to loop for a side effect.
- Forgetting to return a value from a callback.
- Using `reduce()` for simple cases where `map()` or `filter()` would be clearer.
- Mutating objects inside these methods without a clear reason.

## Best Practices

- Use `map()` for one-to-one transformations.
- Use `filter()` for yes-or-no selection.
- Use `reduce()` when the output is a single combined result.
- Name callback parameters after the data, such as `product` or `user`.

## Troubleshooting

If your result contains `undefined`, check that your callback returns a value. If `reduce()` gives the wrong total, confirm the initial value and the accumulator return statement.

## Quick Reference

- Reach for `map()` when the output array should have the same number of items.
- Reach for `filter()` when the output array may have fewer items.
- Reach for `reduce()` when the output should not be a simple one-to-one array transformation.
- If `reduce()` makes the code hard to read, a plain loop may be the better beginner-friendly choice.

## Next Steps

- Review object syntax in [JavaScript Objects Explained](javascript-objects-explained.md).
- Use these methods when rendering lists in [How React Components Work](../02-react-nextjs/how-react-components-work.md).

## Further Reading

- [MDN Array.prototype.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- [MDN Array.prototype.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [MDN Array.prototype.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)


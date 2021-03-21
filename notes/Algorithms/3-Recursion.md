# Recursion

Take a moment to Google the term “recursion.” What do you find? If you're looking for them, recursion jokes exist everywhere in the programming world. After completing this lesson, you too will come to know and love recursion.

### TOPICS

- What Is Recursion?
- Writing a Recursive Function
- When Recursion Can Help

# Learning Objectives

1 of

By the end of this lesson, you'll be able to:

- Define recursion.
- Write the base case and recursive case of a recursive function.
- Identify functions that use recursion and explain why it’s used.

# What Is Recursion?

2 of

Put simply, recursion is when a function calls itself. We know a function can call upon other functions to achieve its goal, but it can also call upon itself.

When your functions start getting too big to read clearly and test easily, you split them up into smaller functions that each perform part of the larger task. A recursive function, however, will achieve a small part of the larger task, then pass the partially completed problem to another call of itself. It’s just another way of breaking down a large problem into smaller bits.

![recursion](../pics/recursion.jpeg)

# A Useless Recursive Function

3 of

Let’s take a look at a function that calls itself and consider what it does. (Warning: Running this program might cause your JS console to stall or crash.)

```js
// Define the function:
function philosopher() {
  console.log('hmm...');
  // Call itself:
  philosopher();
}
// Call the function initially:
philosopher();
```

Why does this function come with a warning? When we call `philosopher()` initially, it prints out "`hmm...`". Then, the function calls `philosopher()` — as in, itself. So, it will once again print "`hmm...`" before calling itself again... forever!

# Fixing the Problem

4 of

Let’s look at another recursive function — one that doesn’t come with a warning label (i.e., won’t crash your computer):

```js
function countDown(num) {
  if (num < 0) {
    return;
  }
  console.log(num);
  return countDown(num - 1);
}
```

This function just counts down from a given number to zero. Notice how the last part of the function calls itself, only with a slightly different argument than the number initially given. This is what makes the function recursive and stops it from running forever into eternity.

# Three Steps to Recursion

5 of

We can break down the process of a recursive function into three steps:

- **Base case:** When the process can stop.
- **Action:** Put that function to work!
- **Recursive case:** The function is called again but with the assurance that progress is being made toward the base case.

Let’s break each part down by looking at our recursive countdown function if we started with 3 as the argument:

```js
function countDown(num) {
  if (num < 0) {
    return;
  }
  console.log(num);
  return countDown(num - 1);
}

countDown(3);
```

# The Base Case

6 of

Here’s the base case for this function:

```js
function countDown(num)
  if(num < 0){
    return;
  }
```

The base case establishes when the recursive function can finally return a specific value and no longer needs to continue calling itself to find that value. Put another way, the base case is where the function bottoms out.

In the countdown function, we first check if the number given is less than `0`. Because `3` is not less than `0`, we can proceed. Once we get below `0`, the countdown is over and the function can complete.

# The Action

7 of

Between the base case and recursive case, the function performs an action. In our countdown function, we simply want to count each number before proceeding to the next one, so we `console.log() 3`:

```js
function countDown(num) {
  if (num < 0) {
    return;
  }
  console.log(num);
}
```

You may see the action introduced by “else,” like below. This doesn’t change the function, it just adds in some plain language to explain what's happening in the function:

```js
function countDown(num) {
  if (num < 0) {
    return;
  } else {
    console.log(num);
  }
}
```

# he Recursive Case

8 of

Finally, we use recursion by calling the `countDown()` function again. Only this time, we feed it the next number in the sequence by providing `num - 1` as the argument:

```js
function countDown(num) {
  if (num < 0) {
    return;
  }
  console.log(num);
  return countDown(num - 1);
}
```

# Knowledge Check

9 of

In plain English, explain what happens when this function reaches the recursive case. (Remember that we've passed in `3` as the argument.)

Hint: There are six things that happen before the base case occurs.

```js
function countDown(num) {
  if (num < 0) {
    return;
  }
  console.log(num);
  return countDown(num - 1);
}

countDown(3);
```

### Answer

Here’s what the function is doing once it gets to the recursive case:

1. Count the number `3`, then call the `countDown()` function again with `2` as the given number.
2. The function makes sure that `2` is still greater than `0`. It is! Proceed.
3. Count the number `2` and call `countDown()` again with 1.
4. The function checks `1` against `0` (it’s greater), counts `1`, and calls `countDown()` with `0`.
5. The `countDown()` confirms that `0` isn’t less than `0`, counts the number `0`, and calls `countDown()` again with `-1` as the given number.
6. Finally, the base case occurs! The “if” check realizes we’ve gone past `0`, into negative numbers, and simply returns to stop the sequence, instead of continuing on with the next few steps.

# Knowledge Check

10 of

If a recursive function calls itself twice in the recursive case, what type of time complexity would we get?

- [ ] Linear: `O(N)`
- [ ] Exponential: `O(2^N)`
- [ ] Logarithmic: `O(Log(N))`
- [ ] Factorial: `O(N!)`

Answer:
Exponential

If each recursive call generates two more recursions, this would resilt in exponential growth, meaning that its complecity would scale at an `N^2` rate. At the first layer, it would recure twice. In the second layer, you would have four recursive calls. The third layer would have eight recursions, and so on.

# Writing Recursive Functions

11 of

There are four basic steps to writing a recursive function:

1. Define your function and parameters.
2. Define your base case and return the computed result.
3. Perform the action step.
4. Return the function with new arguments to make progress toward the base case.

Let’s work through these steps using a JavaScript function that will add all of the numbers in an array. Pop open [a blank CodePen](https://codepen.io/aharri64/pen/RwKbwRv?editors=0012) to follow along! (Hint: Open the console at the bottom of the CodePen to see what happens when your code runs.)

# Step 1: Function and Parameters

12 of

First, let’s write our function. We can use a basic sum function for this problem.

When writing recursive functions, our parameters are important. In this case, we’ll set our parameters as the array we’re in, the index we’re at, and the sum of the numbers so far:

```js
function sumArrayOfNums(arr, index, sum) {}
```

# Even Better Parameters

13 of

With recursive functions, it can be helpful to give your parameters default values to reduce some of the function’s calls.

In our sum function example, we might set the index and sum at `0`. When they’re defined this way, the index and sum don’t need to be provided when calling the function:

```js
function sumArrayOfNums(arr, index = 0, sum = 0) {}
```

# Step 2: Define the Base Case

14 of

Now that our parameters are set, we can add the base case — when the function can stop and return the computed result.

Here, the function can return the sum when the index has gone past the end of the array:

```js
function sumArrayOfNums(arr, index = 0, sum = 0) {
  if (index === arr.length) {
    return sum;
  }
}
```

# Step 3: Give ’Em Something to Do

15 of

Next, add the action step. Here, we’ll add the number at the current index in the array to the sum:

```js
function sumArrayOfNums(arr, index = 0, sum = 0) {
  if (index === arr.length) {
    return sum;
  }
  sum += arr[index];
}
```

# Step 4: Recursion!

16 of

Finally, return the function with new arguments to make progress toward the base case. Here, we indicate `index + 1` so that the function continues moving through the length of the array:

```js
function sumArrayOfNums(arr, index = 0, sum = 0) {
  if (index === arr.length) {
    return sum;
  }
  sum += arr[index];
  return sumArrayOfNums(arr, index + 1, sum);
}
```

Don’t forget to return the recursive function call! Otherwise, the final return value won’t go beyond the second-to-last recursive call. Each recursive call needs to return the value of the next call, so the end result gets passed back up the chain to the very first call of the function (the base case).

In your CodePen, test your function with the array `[2, 4, 5, 8]`. (We’ll do the math for you: You should get `19`.)

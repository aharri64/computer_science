# Search Algorithms

No, learning search algorithms doesn’t mean you’ll be able to hack Google’s — yet. In this lesson, we’ll cover brute force search, which is just as inelegant as it sounds (Spoiler alert: You’ve already been doing it all this time), along with the shiny new binary search algorithm.

### TOPICS

- Brute Force Search
- Binary Search
- Insertion in Binary Search

# Learning Objectives

1 of 17

By the end of this lesson, you'll be able to:

- Understand the Big O complexities of brute force and binary search approaches.
- Describe how binary search works.
- Write a binary search algorithm to find a value in an array.

# Search: It’s Been There All This Time

2 of 17

Programmers, when you were first taught arrays, your instructor most likely asked you to write code to find an element in an array. Or, maybe they asked you to write code to locate the index of an element in an array.

Let’s pretend you had to find the band “Def Leppard” in an array of hair metal bands.

Your final product may have looked something like this:

```js
// Determine if Def Leppard is in the array and find its index if so:
const hairMetal = ["Kiss", "Guns n Roses", "Van Halen", "Sammy Hagar", "Aerosmith", "Twisted Sister", "Motley Crue", "White Snake", "Poison", "Europe"]
let searchTerm = "Def Leppard"
let found = false;
let index = -1;
for(let i = 0; i < hairMetal.length; i++) {
  if hairMetal[i] === "Def Leppard" {
    found = true;
    index = i;
  }
}
if(found) {
  console.log(`${searchTerm} is located at index ${index} in the array`);
} else {
  console.log(`${searchTerm} not found`);
}
```

# And Then You Made it Better

3 of 17

As you were doing it, you probably realized that, once the element or index had been found, the computer didn’t need to keep searching for it. So, you added a `break`, or a statement that told the algorithm to stop looking for the element once it was located:

```js
for(let i = 0; i < arr.length; i++) {
  if arr[i] === "Def Leppard" {
    found = true;
    index = i;
    break;
  }
}
```

This means you were thinking about algorithmic complexity — making sure the algorithm didn’t keep running forever — even if you weren’t aware of it at the time. (Yes, Big O has always been haunting you.)

# And Then You Learned Array Methods

4 of 17

Later on, you probably discovered array methods like `.indexOf()`, `.findIndex()`, and `.find()` and learned to appreciate the elegance they added to your code:

```js
const hairMetal = [
  'Kiss',
  'Guns n Roses',
  'Van Halen',
  'Sammy Hagar',
  'Aerosmith',
  'Twisted Sister',
  'Motley Crue',
  'White Snake',
  'Poison',
  'Europe',
];
// Locate Def Leppard in the array if it’s there:
const index = hairMetal.indexOf('Def Leppard'); // index === -1 because it wasn't found.
```

Your code was elegant indeed but not any more efficient. These methods are basically just fancy `for` loops, so the computer had to scan all the way through the array to know “Def Leppard” wasn’t there.

# Knowledge Check 1

5 of 17

What is the worst case time complexity of a single for loop?
`O(N)` - A `for` loop will iterate once through every element in the input. When we serach through each item in an array, we get `O(N)` complexity.

# Brute Force Search

6 of 17

(video)

- Transcript

In computer science, we use the expression “brute force” to refer to any algorithm that tries every possibility available.

For example: Try every item on the menu to see if any of them involve fried chicken; check every single brand of cereal in the store to see which has the most protein; try on every pair of shoes in the store to make sure you’re finding the best fit and style; you know your long-lost dear friend lives on Ashland Avenue in Chicago, which is 25 miles long, but you’re not sure exactly where, so you knock on every single door on Ashland Avenue until you find her.

In real life, these kinds of problem-solving approaches are typically absurd. You can often use your super-smart, human-level brain to do better. Trying every menu item to see if they have fried chicken might be delicious, but it’s an inefficient — and expensive — approach. Instead, you’d just look under “poultry dishes” on the menu. Or, in the case of choosing shoes, you can use your eyes to judge the style and check the size.

But the computer can’t really do that. And sometimes, neither can you. If you wanted to find the cereal with the most protein, you might actually have to read every box to figure it out!

# But What If I Told You...

7 of 17

That the array was already sorted?

Consider this: Would you rather try to find a word in a dictionary in which all of the words are alphabetized? Or one in which all of the words are in a totally random order?

If we sort our hair metal bands array alphabetically, we can leverage the computer’s special abilities:

```js
hairMetal.sort();
console.log(hairMetal);
// => ["Aerosmith", "Europe", "Guns n Roses", "Kiss", "Motley Crue", "Poison", "Sammy Hagar", "Twisted Sister", "Van Halen", "White Snake"]
// It's now sorted alphabetically!
```

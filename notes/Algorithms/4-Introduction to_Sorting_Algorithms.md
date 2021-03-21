# Introduction to Sorting Algorithms

If you think sorting sounds simple, consider things you’ve had to sort before: your laundry, your taxes, your life... easier said than done, right? The same applies with sorting in programming. In this lesson, we’ll walk through some basic concepts and establish a foundation for learning more complicated sorting algorithms. (Just don’t expect us to help you sort your laundry.)

### TOPICS

- How to Sort
- Stability in Sorting
- Big O for Sorting

# Learning Objectives

1 of 17

By the end of this lesson, you'll be able to:

- Define the two sorting methods and when you’d use each.
- Identify whether a sort is stable or unstable and what impact that can have.
- Explain how Big O complexity applies to sorting algorithms.

# What Is Sorting?

2 of 17

(video)

Sorting in computer science is no different than sorting in real life. It’s taking an unordered collection of stuff, like this pile of Legos, and putting them into an ordered collection of stuff, like these Legos here.

Sorting is the foundation for much more complex algorithms. Do you want to manage customer accounts on your eCommerce site? Search a database for information? Schedule computing jobs to minimize completion time? Behind all of these important processes is a solid sorting algorithm.

If the only thing we’re trying to accomplish is putting things in order, how many sorting algorithms could there be? Surely it can’t be that complicated! You’d be surprised. There are dozens of sorting algorithms! There’s:

- bubble sort
- merge sort
- quick sort
- heap sort
- radix sort
- cube sort
- bucket sort
- shell sort
- tree sort
- insertion sort
- selection sort
- counting sort

And those are just the more common ones!

Each sort we’ll cover has its advantages and disadvantages. It’s important for us to understand why some sorts are bad before we can improve them. As you’ll discover, some of the most intuitive ways to sort are actually pretty terrible!

# Types of Sorting: Comparison Sort

3 of 17

There are two major types of sorting algorithms. The first we’ll cover is **comparison sort**. It does what it says on the tin: It compares two items and decides which one to put first.

If you’re comparing numbers, use their values. If you’re comparing words, use the alphabet. If you’re comparing Lego blocks, use their size, like below.
![comarison](../pics/comparison.gif)

# Big O Notation

Learning about Big O Notation will teach you how to talk about the efficiency of algorithms — that is, how much time and space they need to run — like a computer science veteran. Want to learn how to casually drop “logarithmic complexity” into conversation? Read on!

- Efficiency in Coding
- Speaking Big O
- Big O Classifications

# Learning Objectives

1 of

By the end of this lesson, you'll be able to:

- Explain how Big O notation is used to describe algorithms.
- Define constant, linear, quadratic, logarithmic, and factorial Big O runtimes.
- Analyze algorithms to determine their Big O runtime.

# Understanding the “Worst-Case Scenario”

2 of

Let’s look at our car example again: You’ve bought your dream car and immediately take it out for a joy ride — an extended joy ride. You look at your fuel meter and discover you’re down to your last gallon of gas.

The car dealer had told you that your car gets about 18 miles per gallon. You ask Siri where the nearest gas station is, and she tells you it’s 15 miles away. That’s cutting it awfully close, wouldn’t you say?

Here’s what might be running through your head:

- “In the best-case scenario, could you get 20 miles per gallon instead of 18?”
- “What is the best-case scenario (average driving speed, type of road, etc.)?”
- “What if that last gallon of gas can only get you 14 more miles based on the type of road you’re on now?”

We would describe that last bullet as the worst-case scenario.

# Inefficiency in Coding: The “Worst-Case Scenario”

3 of

In coding, we use the idea of the “worst-case scenario” to compare the efficiency of different algorithms. That way, we know the code will never perform worse — i.e., slower, using up more RAM — than that measurement.

Knowing the best- or average-case performance of an algorithm is useful, too. But worst-case scenario is the standard measure for comparison. (If only car dealers made it that clear!)

# Big O Notation

When it comes to software, we talk about efficiency in terms of Big O notation. Big O comes from the world of math, where it’s used to describe the relationship between two functions based on their growth rates.

In software development, Big O focuses on the efficiency of an algorithm as its input increases. It’s used to describe time complexity or space complexity:

- **Time complexity** refers to the amount of time an algorithm takes to run.
- **Space complexity** refers to the amount of memory or RAM an algorithm needs to run.

Time complexity is a bit more complicated than space complexity, so let’s take a moment to dive into it.

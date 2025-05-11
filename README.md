# Theoretical Sorting

A Computer Science researcher claims to have come up with a sorting algorithm
that can sort arbitrary elements in $O(n)$ time based on comparisons of two
elements at a time. This would be asymptotically faster than any known general
sorting algorithm. The algorithm itself is proprietary and will be sold by a
company.

How would you verify this claim? You may assume that you have access to a
black-box implementation of the sorting algorithm, i.e. you cannot examine the
source code, but you can use it to sort any list you like. Explain in detail
your method for investigating whether X is correct, including any expected
results you would get.

Also give a theoretical argument for why X could or could not be correct, based
on the complexity of the general sorting problem we covered in class.

Add your answers to this markdown file.

## How I would verify the claim and the methods:

Instead of empirically testing, I'd verify the claim by running different compositions of lists (reverse sorted, sorted, randomly sorted) at linearly increasing sizes. If the claim is true, we should see the runtime should increase at the same rate as the input size increases. For example, if a reverse sorted list with 500 elements took 10 seconds, a reverse sorted list of 1000 elements should take 20 seconds, a reverse sorted list of 1500 elements should take 30 seconds, and so on. Then, I'd observe the same pattern for each of the other compositions. If the runtime does not increase proportionally to the input size the claim is false, otherwise this method would show the claim is true.

## Theoretical Argument

The claim that comparison sorting can is linear contradicts our established lower bound for comparison based sorting algorithms

That being that any comparison based algorithm can be represented as a decision tree where:

  - each node is a comparison between two elements
  - the following branch is the outcome of the comparison
  - the resulting leaf is the permutation of the input

In the slides: Complexity of the Sorting Problem:
  - The number of leaves is at least n!.
  - The height of the decision tree is at least ⌈lg(n!)⌉.
  - The number of comparisons made in the worst case is at least ⌈lg(n!)⌉.
  - This is true for any comparison-based sorting algorithm so the complexity of the
      sorting problem is Ω(n log n) (lg(n!) = n lg n according to Stirling’s
      approximation)

However, if the values are known and purposefull like in bucket sort $O(n)$ and radix sort $O(wn)$ that makes the origional more suspicious.
Bucket sort and Radix sort achieve linear or near linear time by:
  - Making assumptions about the input
  - not primarily operating off comparisons
  - trading space for time

This means the claimed algorithm can't truely be comparison based if it's for general, arbitrary inputs.
It likely uses direct addressing or other non-comparison techniques

## In Conclusion

The claim of an $O(n)$ general purpose comparison based sorting algorithm is highly suspisious.
The researcher might have done the following;
  + made a special algorithm made for particular data distribution
  + created something that sways the properties of data types
  + optimized under known conditions
  + miscalculated the asymptotic analysis

An algorithm with linear complexity does not compare two elements at a time without knowing it's input (not arbitrary)

### Sources

[Comparison based sorting](https://www.geeksforgeeks.org/lower-bound-on-comparison-based-sorting-algorithms/)

[Decision Trees](https://scikit-learn.org/stable/modules/tree.html)

[Special-Case vs. General Purpose algorithms](https://cs.stackexchange.com/questions/92321/will-we-ever-achieve-a-on-general-purpose-sorting-algorithm-or-at-least-bet)

"I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice."

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

## How I would verify the claim and the method:

**Empirically Testing** - After running multiple arrays of various increasing sizes (such as n = 10, 100, 1000, and so on),
Measure the actual run time,
Plot each running time against the input size to find the growth pattern
Compare with the runtimes of other algorithms and growth rates like $O(n log n )$ like mergesort on the same inputs

**Finding A Pattern** - Testing for worst case and best case scenarios to see if the claim is misadvertising, giving only
it's best case for marketing purposes. I'd also test on arrays with multiple elements that are the same or on
arrays with various patterns in them in an effort to see if the algorithm has any weakspots with comparisons or shortcuts.

**Testing the Claims** - Making inputs that are as random as possible so the stucture of the input cannot be correlated 
with the performance of the algorithm or if the algorithm is truely comparison based.

### Expected Results

By graphing the runtime compared to the size of the input will tell how true the " $O(n)$ time " holds for real implementation.

This will also expose if all input compositions result in a consistant runtime

Comparing this algorithm to other known algorithms can show if the runtime outperforms $O(n log n)$

## Theoretical Argument

The clain that comparison sorting can is linear contradicts our established lower bound for comparison based sorting algorithms

That being that any comparison based algorithm can be represented as a decision tree where:

  - ech node is a comparison between two elements
  - the following branch is the outcome of the comparison
  - the resulting leaf is the permutation of the input

In the slides: Complexity of the Sorting Problem
  ▷ The number of leaves is at least n!.
  ▷ The height of the decision tree is at least ⌈lg(n!)⌉.
  ▷ The number of comparisons made in the worst case is at least ⌈lg(n!)⌉.
  ▷ This is true for any comparison-based sorting algorithm so the complexity of the
      sorting problem is Ω(n log n) (lg(n!) = n lg n according to Stirling’s
      approximation)


### Sources

[Comparison based sorting](https://www.geeksforgeeks.org/lower-bound-on-comparison-based-sorting-algorithms/)

[Decision Trees](https://scikit-learn.org/stable/modules/tree.html)

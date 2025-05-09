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

**Finding A Pattern** - Testing for worst case and best case scenarios to see if the claim is misadvertising, giving only
it's best case for marketing purposes. 

**Testing the Claims** - Making inputs that are as random as possible so the stucture of the input cannot be correlated 
with the performance of the algorithm or if the algorithm is truely comparison based.

### Expected Results

By graphing the runtime compared to the size of the input will tell how true the " $O(n)$ time " holds for real implementation.

## Theoretical Argument





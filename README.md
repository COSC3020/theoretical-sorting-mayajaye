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

I would verify this claim by using the algorithm to sort all permutations of a
list. Any comparison based algorithm will need to at least look at all of the 
elements of a list which results in a linear time complexity. This means the 
lower bound of X should be $\Omega(n)$. If $O(n)$ is the upper bound, all of 
these inputs should take approximately the same amount since the upper and 
lower bounds of X are the same. If a permutation does not take the expected 
amount of time, that means it has exceeded the upper bound, and X is incorrect.

Theoretically, X could not be correct. Comparison-based algorithms can be 
represented by a binary decision tree since each comparison leads you to a
different permutation. A list of size n has n! permutations, and each permutation
on the tree is a leaf. So, there are at least n! leaves, making the height of the
tree at least log(n!). The worst case input will have to traverse the height of
the tree, so the number of comparisons made in the worst case is at least log(n!).
log(n!) = n log n by Stirling's approximation, so the lower bound of any
comparison based sorting algorithm is $\Omega(nlogn)$, which X violates since its
lower bound is $\Omega(n)$.

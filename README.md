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

I would verify this claim by using the algorithm to sort sorted lists, reverse
sorted lists, and randomly permuted lists of varying sizes. If X does run on 
$O(n)$, as the input size increases, the runtime will increase linearly for each
case. For example, if input size 100 takes 0.1 seconds, input size 100,000 should
take around 1000 times longer, so around 100 seconds since the time should be 
increasing proportionally to the input size. Other performance factors can affect
this time though, so I would graph the runtimes of each case and make sure they 
follow a linear slope. If there are any major outliers, X is incorrect.

Theoretically, X could not be correct. Comparison-based algorithms can be 
represented by a binary decision tree since each comparison leads you to a
different permutation. A list of size n has n! permutations, and each permutation
on the tree is a leaf. So, there are at least n! leaves, making the height of the
tree at least log(n!). The worst case input will have to traverse the height of
the tree, so the number of comparisons made in the worst case is at least log(n!).
log(n!) = n log n by Stirling's approximation, so the lower bound of any
comparison based sorting algorithm is $\Omega(nlogn)$, which X violates since its
lower bound is $\Omega(n)$.

"I certify that I have listed all sources used to complete this exercise,
including the use of any Large Language Models. All of the work is my own, except
where stated otherwise. I am aware that plagiarism carries severe penalties and
that if plagiarism is suspected, charges may be filed against me without prior
notice."

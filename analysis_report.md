# Rigorous Analysis of the Average-Case Time Complexity of Randomized Quicksort

- The average-case time complexity of Randomized Quicksort is \(O(n \log n)\) because, in the average case, we choose an element that is evenly balanced, and recursion divides the array into two equal parts. The recursion depth will be \(O(\log n)\), as the problem size reduces by approximately half at each step.

Let \(T(n)\) be the expected running time of Randomized Quicksort on an input of size \(n\):

\[
T(n) = T(k) + T(n-k-1) + O(n)
\]

Where \(k\) is the number of elements in one partition. Since \(k\) is random, the average value of \(k\) is \(n/2\). So,

\[
T(n) = 2T\left(\frac{n}{2}\right) + O(n)
\]

According to the **Master Theorem**, \(T(n)\) is \(O(n \log n)\).

## Worst-Case Time Complexity

The worst-case time complexity of Randomized Quicksort is \(O(n^2)\). This occurs when the pivot consistently divides the array in the most unbalanced way possible, such as when the pivot is always the smallest or largest element.
This situation can occur if the array is already sorted in ascending or descending order, and the pivot is always chosen as the first or last element.

---
## Random pivot selection

As we discussed the worst case scenario above, by choosing a random pivot, its highly unlikely that the division will be unbalanced. This avoids the case where the array is already sorted or is in reverse order. Basically the worst case could be avoided. This is not just the first division, even on the subsequent recursive by having the random pivot we can avoid \(O(n^2)\)time. 

## Emperical analysis
Input Size: 100, Distribution: random
Deterministic Quicksort Time: 0.00012 seconds
Randomized Quicksort Time: 0.00016 seconds

Input Size: 100, Distribution: sorted
Deterministic Quicksort Time: 0.00037 seconds
Randomized Quicksort Time: 0.00014 seconds

Input Size: 100, Distribution: reverse_sorted
Deterministic Quicksort Time: 0.00040 seconds
Randomized Quicksort Time: 0.00014 seconds

As noted, when the random pivot is chosen results are a lot more faster. On the other hand, when the array is not sorted and deterministic approach is used, it outweights by a little. 
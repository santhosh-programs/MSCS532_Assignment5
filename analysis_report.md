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
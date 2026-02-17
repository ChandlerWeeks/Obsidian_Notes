# Prerequisites: Proofs
## Proof by Induction
Parts of proof by Induction
Theorem: What we want to prove by induction
Basis: a case that will need to be held
Inductive Hypothesis: What will need to be shown for the case to hold
Inductive Step: Where we show that the hypothesis holds

Theorem -> Basis (true for any n=1) -> Hypothesis (true for any n>=1) -> Step show that f(n) = g(n). 

# Proof by contradiction

Given a prediction, prove that the opposite isn't true, and therefore the basis holds. 
# Chapter 3: Asymptotic and Growth Functions

## Big Notation

- Big-O: $f(x) = O(g(x))$ if there exists some constant c, where $f(x) < c*g(x)$ for all $x > x_0$. (Upper bound)
- Big-$\Omega$:  $f(x) = \Omega(g(x))$ if there exists some constant c, where $f(x) > c*g(x)$ for all $x > x_0$. (lower bound)
- Big-$\Theta$:  $f(x) = \Theta(g(x))$ if there exists some constants $c_1$ and $c_2$ , where $c_1*g(x) > f(x) > c_2*g(x)$ for all $x > x_0$. (tight asymptotic bound). 

## Little Notation

- little-o: Limit of the ratio of f(n)/g(n) as n -> infinity is 0. (tight upper bound)
- little-$\omega$:  Limit of the ratio of f(n)/g(n) as n -> infinity is infinity. (tight lower bound)
- little-$\sim$:  Limit of the ratio of f(n)/g(n) as n -> infinity is 1. (Exact bound, no less or more)

# Chapter 4: Divide and Conquer / Solving Recurrences
A general divide and conquer recurrence follows this formula:

$T(n) = a*T(n/b) + f(n)$
Where
- a = Number of recursive calls
- n/b = size of each sub problem
- f(n) is the number of non recursive work per call

**_Simple Linear Recursion_**
T(n) = T(n-1) + 1
T(1) = 1
T(n) = O(n), because the work is done in linear time. 

**_Binary Search_**
T(n) = T(n/2) + 1
T(n) = O(log(n)), because the problem is halved each time

**_Merge Sort_**
T(1) = 1
T(n) = 2T(n/2) + (n-1), because we perform n operations on two two subproblems
T(n) = nlogn

**_Bubble Sort_**
T(n) = T(n-1) + (n-1),
So T(n) = n(n-1)/2

**_Towers of Hanoi_**
T(n) = 2T(n-1) + 1 if n>1
So T(n) = $2^n - 1$

### On Matrix Multiplication
We know that matrix multiplication (go through each row, and for each column, add the values).
We can recursively solve this with 8 multiplies and 4 adds. 

Therefore $T(n) = 8T(n/2) + \Theta(n^2)$. 
So T(n) = O(log_2(8)) = O(n^3). 

However, we can use Strassen's algorithm to optimize this to only have 7 multiplies, but 22 adds. 
$T(n) = 7T(n/2) + \Theta(n^2)$
So, $T(n) = O(log_27) = O(n^2.8+)$. 

## Master Theorem

The master theorem accepts a recurrence which follows the pattern. 
 $T(n) = aT(n/b) + f(n)$, where $a>=1$ and $b>1$. 

1. If $f(n) = O(n^{log_ba-\epsilon})$ for some constant $\epsilon > 0$ then $T(n) =\Theta(n^{log_ba})$  
2. If $f(n) = \Theta(n^{log_ba-\epsilon})$ then $T(n) =\Theta(n^{log_ba}lg(n))$  
3. If $f(n) = \Omega(n^{log_ba+\epsilon})$ for some constant $\epsilon > 0$ then $T(n) =\Theta(f(n))$  

# Sorting Algorithms
Terms for Sorting Algorithms
Key Comparisons: The number of comparisons done in the algorithm
Record Exchanges: The number of swaps performed by the algorithm
## Bubble Sort
Makes comparisons forward so that the highest value is moved to the last element. Swaps nearby values when in wrong order. 
- **Worst/Average Case**: Quadratic number of comparisons and record exchanges. 
- **Best Case**: Linear with the perfect input. 
- **Stability**: Stable when keys are equal; 
## Selection Sort
Find the Nth smallest element, and put it at location n
 - **Worst/Average Case**: Quadratic number of key comparisons, but linear number of swaps. 
- **Best Case**: Quadratic number of key comparisons, but 0 swaps. 
- **Stability**: Stable when you only select the first instance of the Nth smallest value. 
## Insertion Sort
Go through each item in the array and insert it into a new array. 
**Linear Insertion Sort**: Use a linear search to determine where to put the new item. 
**Binary Insertion Sort**: 
- **Worst/Average Case**: Quadratic number of swaps, but nlog(n) comparisons for binary search insertion sort. (quadratic for linear). 
- **Best Case**: Quadratic number of comparisons, n log n for binary insertion, But 0 record moves. 
- **Stability**: Linear insertion sort is stable, binary insertion sort can be implemented in a stable way. 

## Counting Sort
Count the number number of records whos keys are strictly smaller. 
- **Best/Worst/Average Case**: Quadratic number of swaps, but nlog(n) comparisons for binary search insertion sort. (quadratic for linear). 
- **Stability**: Stable when only counting cases smaller
## Merge Sort
Divide the problem into subproblems, then work back up merging the divided problems. Mergesort -> mergesort -> merge
- **Worst/Best/Average Case**: linearithmic, (nlgn). 
- **Stability**: Stable, swaps are never in the same position. 
## Heap Sort
Build a heap, and extract the data from it, then reheapify, until every value is checked.

- **Worst/Average/Best Case**: Always linearithmic number of comparisons and record swaps. 
- **Stability**: Stability is preserved, assuming you don't swap the child of equal nodes when heapify. 
## Quick Sort
Like merge sort, but does the sorts down rather than merging back up. 
Partion -> quicksort(left) -> quicksort(right). If the leftmost 

- **Worst/Average/Best Case**: quadratic worst case, but can be made into n log n by selecting a median in linear time. Low constant of proportionality for comparisons. 
- **Stability**: Stable when using a random pivot. 

## Shell Sort
Divides the list into sub-lists, and performs insertion sort on them. Takes a log number of passes, but not n number of passes; 
**Worst/Average/Best Case**: Always n^1.5
**Stability**: Unstable

## Radix Sort
Radix means base. Group digits that have the share the same significant position. Sort by the digit one column at a time. Starts at the least significant digit (right to left). 

Radix sort does NO comparisons. Instead, you compare a digit, not a key. It cannot be compared to the other sorting algorithms in the same way. 
## Bucket Sort
Pass through a file, but put them in location not based on digit. Instead, use a preset size, like 20, 50, or 100. Its a little more error prone, but radix sort is an implementation of this.

Stable, if implemented correctly. 
## Hybrid Sort
Very niche situation, where you use a combination of sorting algorithms.  

# Optimizing Quicksort
Quicksort is O(n^2) because a bad pivot can skew our results. We have a few solutions to choosing a pivot, but the best way is by choosing the median of medians. 

## Median of Medians
Steps:
1. Chose an odd r>1 (5, 7, 9)
2. Divide the list L into n/r subfiles
3. Find the median of each subfile
	1. Just use insertion sort or something similar
4. Find the median of medians
	1. Recursively find the median of the given file. 
5. Use the median of medians as a partition. 
	1. If the median of medians is the median, it will be the center index for the left/right array
	2. if it is to the left of the center, call median of medians on the right, and vice versa. 
	3. We know we will always get rid of $\frac{r+1}{4r}$ elements. 

Recurrence Relation for Median of Medians

$T(\frac{n}{r}) + T(n * \frac{3r-1}{4r}) + cn$


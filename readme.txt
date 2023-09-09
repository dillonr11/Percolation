/* *****************************************************************************
 *  Operating system:
 *  Compiler:
 *  Text editor / IDE:
 *
 *  Have you taken (part of) this course before:
 *  Have you taken (part of) the Coursera course Algorithms, Part I or II:
 *
 *  Hours to complete assignment (optional):
 *
 **************************************************************************** */

Programming Assignment 1: Percolation


/* *****************************************************************************
 *  Describe the data structures (i.e., instance variables) you used to
 *  implement the Percolation API.
 **************************************************************************** */

We used a 2D array to create our grid, because it represents an n x n grid the
best.  It was also easy to locate the correct site to open or check because you
can simply use the coordinates of the grid.

/* *****************************************************************************
 *  Briefly describe the algorithms you used to implement each method in
 *  the Percolation API.
 **************************************************************************** */
open(): We checked if the surrounding sites were open, and if they were, we
created a union between them.
isOpen(): We used the coordiantes to find the right site and check if it is
equal to true.
isFull(): We used the coordinates to find the right site and check if it is in
the same tree as the virtual top node.
numberOfOpenSites(): We incremented numOpen every time open was called, and
then return numOpen.
percolates(): We simply checked to see if the bottom virtual node was in the
same tree as the top virtual node.

/* *****************************************************************************
 *  Perform computational experiments to estimate the running time of
 *  PercolationStats.java for various values of n and T when implementing
 *  Percolation.java with QuickFindUF.java (not QuickUnionUF.java). Use a
 *  "doubling" hypothesis, where you successively increase either n or T by
 *  a constant multiplicative factor (not necessarily 2).
 *
 *  To do so, fill in the two tables below. Each table must have 5-10
 *  data points, ranging in time from around 0.25 seconds for the smallest
 *  data point to around 30 seconds for the largest one. Do not include
 *  data points that take less than 0.25 seconds.
 **************************************************************************** */

(keep T constant)
 T = 100
 multiplicative factor (for n) = 1.1

 n          time (seconds)       ratio         log ratio
--------------------------------------------------------
100             1.628
110             2.343               1.439           3.819
121             3.387               1.446           3.869
133             4.783               1.412           3.619
146             6.913               1.445           3.862
161             9.961               1.441           3.833
177             14.661              1.472           4.056
195             20.984              1.431           3.760


(keep n constant)
 n = 100
 multiplicative factor (for T) = 2

 T          time (seconds)       ratio         log ratio
--------------------------------------------------------
100             1.665
200             3.252               1.953          .966
400             6.240               1.919          .940
800             12.54               2.010          1.007
1600            24.984              1.992          .994
3200            49.15               1.967          .976
6400            98.205              1.998          .999


/* *****************************************************************************
 *  Using the empirical data from the above two tables, give a formula
 *  (using tilde notation) for the running time (in seconds) of
 *  PercolationStats.java as function of both n and T, such as
 *
 *       ~ 1.32*10^-12 * n^3.83 * T^.980
 *
 *  Briefly explain how you determined the formula for the running time.
 *  Recall that with tilde notation, you include both the coefficient
 *  and exponents of the leading term (but not lower-order terms).
 *  Use two significant figures for each coefficient and exponent
 *  (e.g., 5.3*10^-8 or 5.0).
 **************************************************************************** */

QuickFindUF running time (in seconds) as a function of n and T:

    ~ 1.32*10^-12 * n^3.83 * T^.980



/* *****************************************************************************
 *  Repeat the previous two questions, but using WeightedQuickUnionUF
 *  (instead of QuickFindUF).
 **************************************************************************** */

(keep T constant)
 T = 100
 multiplicative factor (for n) = 1.25

 n          time (seconds)       ratio         log ratio
--------------------------------------------------------
500             1.522
625             2.45                1.61            2.134
781             4.018               1.64            2.217
976             6.835               1.70            2.378
1220            12.368              1.809           2.656
1525            22.183              1.794           2.619


(keep n constant)
 n = 100
 multiplicative factor (for T) = 2

 T          time (seconds)       ratio         log ratio
--------------------------------------------------------
500             .289
1000            .546                1.889           .918
2000            1.04                1.905           .929
4000            2.08                2               1
8000            3.792               1.823           .866
16000           7.981               2.105           1.074
32000           15.386              1.928           .947


WeightedQuickUnionUF running time (in seconds) as a function of n and T:

    ~ 7.51*10^-9 * n^2.4 * T^1



/* *****************************************************************************
 *  Known bugs / limitations.
 **************************************************************************** */

Our percolation class does not handle backwash.


/* *****************************************************************************
 *  Describe whatever help (if any) that you received.
 *  Don't include readings, lectures, and precepts, but do
 *  include any help from people (including course staff, lab TAs,
 *  classmates, and friends) and attribute them by name.
 **************************************************************************** */

Partner: Dillon Remuck
Went to Darius' office hours.

/* *****************************************************************************
 *  Describe any serious problems you encountered.
 **************************************************************************** */

None.


/* *****************************************************************************
 *  List any other comments here. Feel free to provide any feedback
 *  on how much you learned from doing the assignment, and whether
 *  you enjoyed doing it.
 **************************************************************************** */

Very satisfying to get working.

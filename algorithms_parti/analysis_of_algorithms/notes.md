# Observations
## measuring the running time
**empirical analysis** run the program for various input sizes and measure running time.

**data analysis** plot running time T(N) vs. input size N using log-log scale, find regression - fit straight line through data points then use hypothesis to predict the running time - **prediction and validation** 

**doubling hypothesis** quick way to estimate b in a power-law relationship.

**experimental algorithmics** system independent effects and system dependent effects. bad new is difficult to report.

# Mathematical models
## total running time
**total running time = sum of cost x frequency for all operations**
system dependent effects again!. and hardware 

** estimating a discrete sum**
**in principle** accurate mathematical models are available
**in practice** formulas can be complicated and advanced mathematics might be required, and we r going to use APPROXIMATE models in here
## Rather than counting every little details, we take some basic operation maybe the most expensive and or and or the on that's executed that most often, and the one that costs time frequency is that highest
### simplification 1: cost model usie some basic operation as a proxy for running time.
### simplification 2: tlde notation estimate running time (or memory) as a function of input size N, ignore lower order terms(when N is large, terms are negligible, when N is small, we dont care.


# Order of growth classifications

** good news ** the small set of functions
1-constant, log N-logarithmic, N-linear, N log N-linearithmic, N^2-quadratic, N^3-cubic, and 2^N - exponential
**suffices to describe order-of-growth**

**constant** for statement and example: add two numbers and T(2N)/T(N) = 1
**logarithmic** for divide in half and example: binary search T(2N)/T(N) ~ 1 notes for typical code framework: "for loop or while loop but N=N/2"
**linear** for loop and example: find the maximum T(2N)/T(N) = 2-two times notes for typical code framework: "for loop with i++"

**linearithmic** for divide and cnquer and example: mergesort T(2N)/T(N) ! 2 notes for typical coode framework: "see mergesort"

**quadratic** for double loop and example check all pairs T(2N)/T(N) = 4 notes for typecal code framework: "nested loopwith i and j to go through all pairs"

**cubic** for triple loop and example check all triples T(2N)/T(N) = 8

**exponential** for exhaustive search and example is check all subsets and see combinatorial search T(2N)/T(N) = T(N).

## practical implocations of order-of-growth
**we prefer linear and linearithmic** because we need efficient and effective to retrieve the bi or tribilion data.

**binary search demo** given a sorted array and a key, find the index of the key in the array?>
**implementation** compare key against "middle entry" of array. || too small, go left || too big go right || equal, found and print the index.

## an N^2logN algorithm for 3-sum

### typecally faster order of growth leads to faster algorithms

# Theory of algorithms
## types of analyses
the runningtime will be somewhere between the best case and the worst case
### best case
lower bound on cost.
determined by **easiest** input.
provides a goal for all inputs.

### worst case
upper bound on cost.
determined by **most difficult** input.
provides a guarantee for all inputs.

### average case 
expected cost for random input.
need a model for **random** input
provides a way to predict performance.


## theory of algorithms: example1
### goals:
establish "difficulty" of a problem
then, develop "optimal" algorithms

**upper bound** a specific algorithm.
ex: brute-force algorithm for 1 sum: look at every array entry.
running time of the optimal algorithm for 1-sum is O(N)-it's less than an constant time N for some constant

**lower bound** proof that no algorithm can do better.
ex: HAVE TO EXAMINE ALL n entries ( any unexamined one might be 0).
running time of the optimal algorithm foor 1-sum is omega of (N).

**optimal algorithm**
lower bound equals upper bound => it is optimal

ex2 with 3-sum
**upper bound a specific algorithm.**
ex. improved algorithm for 3-sum.
running time of the optimal algorithm for 3-sum is O(N^2logN) (using insertion sort with N^2 and binary search with logN)
**lower bound** proof that no algorithm can do better.
ex: have to examine all N entries to solve 3-sum.
running time of the optimal algorithm for solving 3-sum is ogema(N).
**open problems** 
optimal algorithm for 3-sum? **because there is some gap between upper bound and lower bound (best case and worst case) so no one know even know if there;s a algorithm whose running time is less than N^2logN.

## Algorithm design approach
### start
develop an algorithm 
prove a lower bound

## gap?
lower the upper bound ( it's easier and discover a new algorithm).
OR raise the lower bound (more difficult).
## we should be focusing on the properties of the input and finding algorithms that are efficient for that input.## COMMON MISTAKE: interpreting big-Oh as an appriximate model,
## THIS COURSE: focus on approximate models: use Tilde-notation. because it more accurately describes the function - it provides both an upper and lower bound on the function as well as the coefficient of the leading term.

# MEMORY
## basics
bit 0 or 1
byte 9 bits
megabye(MB) 1million or 2^20 bytes
gigabyte(GB) 1billion or 2^30 bytes.

## old machine we used to assume a 32-bit machine with 4 byte pointers.

## modern machine we now assume a 64 bit machine with 8 byte pointers
can address more memory
pointers use more space
**primitive types**
boolean bytes 1
byte 1 byte
char 2 byte
int 4 byte
float 4 byte
long 8
double 8

**one-dimensional arrays**
char[] 2N + 24
int[] 4N +24
double[] 8N + 24
**for two-dimensinal rrays**
char[][] ~2M N bytes
### typical memory usage for objects in java

object overhead 16 bytes.
reference 8 bytes.
padding each object use a multiple of 7 bytes.

ex: a date object uses 32 bytes of memory
public class Date {
	private int day;
	private int month;
	private int year;
		
}
the total memory usage for Date object in Java = 16bytes(object overhead) + 3x4bytes of ints + 4 bytes of paddin g = 32bytes

ex2 a virgin string of length N use ~ 2N bytes of memory.
char[] value; 8 bytes for referencing to array.
2N + 24bytes (char[] array)
}
}

## typical memory usage summary
### total memory usage for a data type value:
### shallow memory usage dont count referenced objects
### deep memory usage: if array entry or instance variable is a reference, add memory (recursively) for referenced object.


#  Lecture 2

### Definition of algorithm:

A well defined finite instruction to solve a given computational problem.



### Word-RAM model

##### A model of computation that a random-access machine can do bitwise operation on a single word of w bits.

- It works with size w bits, which means it can store integer up to $2^w$ 
- Word size matches problem size(for a problem of size n, $w\geq \log n$). The model allows bitwise operations such as arithmetic and logical shifts to be done in constant time. 
- The number of possible values is *U*, where![{\displaystyle U\leq 2^{w}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d0df364eaa8c181670bac239cff1506bb395981a). (This is important, this means the result of a programs never exceed the word size)



### Count number of operations(Example):

![Screen Shot 2022-04-16 at 9.37.33 AM](/Users/mcr/Library/Application Support/typora-user-images/Screen Shot 2022-04-16 at 9.37.33 AM.png)

### Asymptotic Analysis

Estimate the rate-of-growth of runing time of an algorithm:

- $O$-notation   (Upper bound)
- $\Omega$-notation   (Lower bound)
- $\Theta$-notation   (Tight bound)

#### O-notation

We definine $f(n)=O(g(n))$ If $\exist c, n_0>0: 0\leq f(n)\leq c\cdot g(n) $ for $n\geq n_0$

#### $\Omega$-notation

We define $f(n)=\Omega(g(n))$ if $\exists c,n_0>0: f(n)\geq c\cdot g(n) \geq 0$ for $n \geq n_0$

##### IMPORTANT: O-notation is an upper-bound notation. It makes no sense to say f(n) is at least $O(n^2)$.



#### $\Theta$-notation

We define $f(n)=\Theta(g(n))$ if $\exists c_1,c_2,n_0 > 0:$ $0 \leq c_1\cdot g(n)\leq f(n) \leq c_2\cdot g(n)$, for all $n\geq n_0$



#### $o$-notation

We define $f(n)=o(g(n))$ if $\forall c >0$: $\exists n_0>0:$ $f(n)< c\cdot g(n)$ for all $n\geq n_0$



#### $\omega$-notation

We define $f(n)= \omega(g(n))$ if $\forall c>0: \exists n_0>0: f(n)>c\cdot g(n)$ for all $n\geq n_0$



### Limit theorem

- $\color{red}{\lim_{n\rightarrow \infty}\frac{f(n)}{g(n)}<\infty: f(n)=O(g(n))}$ 			(Intuitively, if $f(n)=\omega(g(n)): \lim_{n\rightarrow \infty}\frac{f(n)}{g(n)}=\infty$, takes contrapotively)

- $\lim_{n\rightarrow\infty}\frac{f(n)}{g(n)}=\infty$:$f(n)=\omega(g(n))$

- $\color{red}{\lim_{n\rightarrow\infty}\frac{f(n)}{g(n)}>0:f(n)=\Omega(g(n))}$              (Intuitively, if $f(n)=o(g(n)): \lim_{n\rightarrow \infty}\frac{f(n)}{g(n)}=0$, takes contrapotively)

- $\lim_{n\rightarrow\infty}\frac{f(n)}{g(n)}=0$:$f(n)=o(g(n))$

- $0<\lim_{n\rightarrow\infty}\frac{f(n)}{g(n)}<\infty$:$f(n)=\Theta(g(n))$



### Relationship between $o,O,\omega, \Omega,\Theta$

- $f(n)=O(g(n)) \rightarrow f(n)\neq \omega(g(n))$

- ##### $f(n)= \omega(g(n))\rightarrow f(n)\neq O(g(n))$

- $f(n)= \omega(g(n))\rightarrow f(n)\neq \Theta(g(n))$

- $f(n) = \Omega(g(n)) \rightarrow f(n)\neq o(g(n))$

- $f(n)= o(g(n))\rightarrow f(n)\neq \Omega(g(n))$

- $f(n)= o(g(n))\rightarrow f(n)\neq \Theta(g(n))$

- $f(n)= \Theta(g(n))\rightarrow f(n) \neq o(g(n)) $

- $f(n)= \Theta(g(n))\rightarrow f(n) \neq \omega(g(n)) $



#### Properties of Big-O

- Transitivity:
  - $f(n)=\Theta(g(n))\land g(n)=\Theta(h(n)) \rightarrow f(n)=\Theta(h(n))$
  - $f(n)= O(g(n))\land g(n)=O(h(n))\rightarrow f(n)=O(h(n))$
  - $f(n)= \Omega(g(n)) \land g(n)= \Omega(h(n))\rightarrow f(n)=\Omega(h(n))$
  - $f(n)=o(g(n))\land g(n)=o(h(n))\rightarrow f(n)= o(h(n))$
  - $f(n)=\omega(g(n))\land g(n)=\omega(h(n))\rightarrow f(n)=\omega(h(n))$

- Refletive:
  - $f(n) = \Theta(f(n))$
  - $f(n)=O(f(n))$
  - $f(n)=\Omega(f(n))$

-  Symmetric
  - $f(n)=\Theta(g(n))\rightarrow g(n)=\Theta(f(n))$

- Complementary
  - $f(n)=O(g(n))\rightarrow g(n)=\Omega(f(n))$
  - $f(n)=o(g(n))\rightarrow g(n)=\omega(f(n))$

### Some concrete example:

1. Adversial wordle
2. Fibonacci number:
   - Recursive algortihm
   - Iterative algorithm

3. Sorting
   - Insertion sort





# Lecture 3

### Iteractive algorithm: Algorithm with one or multiple loops, sequentially operating on the user input.



### Proof of correctness of iteractive algortihm

- True before the first iteration
- If it's true before one iteration, it remains true after the iteration
- If it's true after the last iteration, it implies the correctness of the algorithm



##### Invariant: a condition is true at the begining of the iteration and is correctly maintained through the whole algorithm and can imply the correctness at the end of algorithm.



### Some concrete example:

1. Sorting

   - Insertion sort: prove the correctness of insertion sort

     ##### ![Screen Shot 2022-04-16 at 8.00.17 PM](/Users/mcr/Library/Application Support/typora-user-images/Screen Shot 2022-04-16 at 8.00.17 PM.png)Proof:

     1. ##### Step 1: what is the variant?

        Here the variant is "A[1...j-1] is the sorted list of elements of A[1...j-1]"

     2. ##### Step 2: Prove that the invariant is true before the first iteration

        A[1] is trivially sorted before the first iteration

     3. ##### Step 3: Prove that if the invariant is true before one iteration, it holds true after the iteration

        3.1 Assume A[1...j-2] is sorted of elements originally in A[1...j-2], 

        3.2 Line 6 ensures that any elements larger than A[j-1] are shifted exactly one place right

        3.3 Line 8 assigns value of A[j-1] to the position got by shift

        3.4 It can be implied from 3.2 that every element on the left of the position is smaller than the new value and every element on the right of the position is larger than the new value.

        3.5 Any violation of position to the sorted position will violate at least one of 3.1, 3.2, 3.2, 3.3, and 3.4

        3.6 Therefore the array is sorted after the iteration

     4. ##### Step4: Prove that when the algorithm terminates, the invariant proves the corretness of algorithm

        4.1 After the the first iteration the array A[1...n] is sorted by the invariant, which proves the correctness of the algorithm.

### Analysis of the time complexity of interative algorithm

Usually simple, just find the operation in O(1) first and then check number of excution of O(1) operation in nested loops from center to outside.

## Divide-and-Conquer(Recursively)

- Divide: divide a problem into subproblems that are the same problem but with less instance
- Conquer: If the problem is small enough to solve, solve it directly
- Combine: Combine the solution to subproblem to the solution of the original problem.



### Proof of correctness of recursive algorithm

- Use strong induction
  1. Prove the correctness of the base case
  2. Assume the algorithm works for all smaller cases, prove that the algorithm holds true for a bigger case

### Analysis of time complexity of recursive algorithm

- Analyze on the time complxity of conquering(the time complexity where the algorithm can be solved direcly), usually O(1)
- Analyze on the time complexity relations on each combination: that is:
  - The time complexity of a problem = Sum of time complexity of all subproblems + time complexity to combine the subproblems

- There are several common forms of relation ship:
  - $T(n)= a\cdot T(n-b)+f(n)$
  - $T(n)= a\cdot T(n/b)+f(n)$
  - $T(n)= a_1\cdot T(n-b_1)+ a_2\cdot T(n-b_2) + f(n)$
  - $T(n)= a_1\cdot T(n-b_1)+ a_2\cdot T(b_2) + f(n)$

​	

### Ways to solve a recurrence:

- **Recursion tree**: draw the tree and
- **Master method**: for format of  $T(n)=a\cdot T(n/b)+f(n)$
- **Substitution method**: Guess and prove with math induction



### Master's method

Compare $f(n)$ with $n^{\log_b a}$

- Case 1:  if $f(n)=O(n^{\log_b(a)-\epsilon})$ (i.e. f (n) grows polynomially slower than $n^{\log_ba}$)

  ​					then $T(n)=\Theta(n^{log_b a})$

- Case 2: if $f(n)= \Theta(n^{log_b(a)}\cdot \lg^k n)$ for some constant $k>0$  

  ​                    $T(n)=\Theta(n^{\log_ba}\cdot\lg^{k+1}n)$

- Case 3: if $f(n)=\Omega(n^{\log_b(a)+\epsilon})$ for some constant $\epsilon>0$

  ​                   $T(n) = \Theta(f(n))$

  ##### Regularity condition(another condition of Case 3):

  ​     if $a\cdot f(n/b)\leq c\cdot f(n)$ for some constant c<1



### Substitution method

1. Guess the time complexity
2. Verify by induction



### Concrete Example:

- #### HANOI-Tower

  ```
  HANOI(n,src,dst,tmp):
  	while n>0:
  		HANOI(n-1, src, tmp, dst)
  		MOVE the nth disk from src to dst
  		HANOI(n-1, tmp, src, tmp)
  ```

  #### Proof of correctness:

  RTBD

  #### Analysis of time complexity:

  - $T(n) = 2 \cdot T(n-1)+1$

    Claim: $T(n) = 2^n-1$

    ##### Proof: RTBD 

- #### MERGE-SORT

  ```
  MERGE-SORT(A,1,n):
  	if (q>n):
  		SORT A with insertion sort
  	else:
  		q = (1+n)/2
  		MERGE-SORT(A,1,q)
  		MERGE-SORT(A,q+1,n)
  		MERGE(A,1,q,n)
  		
  ```

#### 	Analysis of time complexity:

​		- $T(n)= 2\cdot T(n/2)+\Theta(n)$



> 📔 <span style="color:#3333ff">**NOTE:**</span>
>
> In terms asymptotic analysis, it doesn't matter for $\lfloor n/2\rfloor $ or $\lceil n/2 \rceil$,  can just use (n/2)



- #### Powering a number

Problem:  $f(n,m)= a^n \mod m$

- Instance: $O(\log n), O(\log m)$

Observation: $f(a+b,m)=f(a,m)*f(b,m)$

##### $O(n)$ solution (divide and conquer ):

1. Divide: $f(n,m)=f(n-1,m)*f(1,m)$
2. Conquer: f(1, m) can be solved in $O(1)$
3. Combine: $f(n,m)=f(n-1,m)*f(1,m)$

$T(n)= T(n-1)+O(1)$, which is $O(n)$



##### $O(\log n)$ solution

1. Divide: 

   a. $f(n,m)=f(\lfloor n/2 \rfloor,m)^2$ if n is even

   b. $f(n,m)= f(1,m)\cdot f(\lfloor n/2 \rfloor)^2$  if n is odd

2. Conquer: $f(1,m)$ can be solved in $O(1)$

3. Combine:

   a. $f(n,m)=f(\lfloor n/2 \rfloor,m)^2$ if n is even

   b. $f(n,m)= f(1,m)\cdot f(\lfloor n/2 \rfloor)^2$  if n is odd

$T(n) = 2\cdot T(n/2)+O(1)$, which is $O(\log n)$



# Lecture 7

### Amortised analysis

Amortised analysis is the analysis of a sequence of operations to show that the average cost of each operation is small while some single operation may be expensive.

### Definition of O(g(m,n)), or multiple-variable instance asymptotic analysis:

Given an function $f(m,n)\geq 0$, we say $f(m,n)\in O(g(m,n))$ if $\exists c,n_0,m_0>0\text{ such that }f(m,n)\leq c\cdot g(m,n)$ for all  $n\geq n_0\text{ \color{red}{or} }m\geq m_0$



### Types of amortised analysis:

- Aggregate method: simple but less precise
- Accounting method: allowing specific amortised cost to each operation
- Potential method: allowing specific amortised cost to each operation



#### Accounting method(Banker's method)

##### Key idea:

- the amortised cost $c(i)$ is fixed for each operation while the true cost $t(i)$ Varies depending on when the operation is called; 
- Pay extra amount for cheap operation as credit prepared in advance for the rare, expensive opeation.

##### Necessary condition to apply accounting method:  $\sum_{i=0}^n t(i)\leq \sum_{i=1}^n c(i)$, intuitively this means that 	the amount of money in the bank never drops below 0.

The total amortized cost provides an upper bound on the total true cost.





#### [Potential method](https://en.wikipedia.org/wiki/Potential_method#cite_note-gt-ad-1)

- $\phi:\{S\}\rightarrow \mathbb{Z}_{\geq 0}$, where S is any state of computer or data structure
- $\phi(0)$:  The initial state
- $\phi(i)$: The state after ith operation
- $c:$ the amortised cost
- $t:$ the true cost

$c(i) = t(i) + C\cdot (\phi(i)-\phi(i-1))$, where C is a constant across the analysis(The C may be omitted because the constant does not affect the time complexity of big O)

##### Necessary condition:

- $\forall i\in\{1,...,n\}: \phi(i)\geq \phi(0)$



> 📔 <span style="color:#3333ff">**note:**</span>
>
> Intuitively, the potential method means the depts that a state is accounted for but not paid yet. It's like counting the energy stored in that state





### Concerete example:

#### 1. Binary counter:

```
BINARY-COUNTER(A):
	i <- 0
	while i< A.length and A[i]==1:
		A[i] = 0
		i <- i+1
	if i < length[A]:
		A[i] = 1
```

The general objective of the analysis is to count the number of time of bit flipping.

- T(n) = total number of bit flipped during n increment

- Aim: get a tight bound for T(n):

  ##### Aggregate method

    Define the state:

  1. t(i): the number of flipings in ith increment

  2. f(j): the number of flippings of jth bit

     - f(0) = n	: every increment will flips bit 0
     - f(1) = n/2    : every two increments will flip bit 1 once
     - f(2) = n/4     : every four increments will flip bit 2 once
     - ...

     $T(n)=\sum_{i=0}^{m} n/(2^i)= n\cdot \frac{1-\frac{1}{2^m}}{1-\frac{1}{2}}<2n$

     Hence the average cost of a single operation is O(1)

     

  ##### Accounting method

  Define the amortised cost of each flips as follows:

  - Flips from 0 to 1: 2
  - Flips from 1 to 0: 0

  The observation is that: each bit 1 in the the array has extra 1 in bank and this 1 can be used to set 1 to 0 later.

  **Claim: each increment only takes 2**

​		proof: let i be the first 1 from right to left after the increment, then  all the bits on right of i must be 1 	      		  before the increment, then all these bit 1s have extra 1 in the bank and hence can pay by 		      					themselves. Only the bit i should take 2 to increment from 0 to 1

​		Hence the amortized cost of n Operation$\leq 2\cdot n= O(n)$

 

> 📔 <span style="color:#3333ff">**Conclusion 1:**</span>
>
> Try find different ways to represent the states, can  be the state of of operation executed, or certain part in the data structure.

> 📔 <span style="color:#3333ff">**Conclusion 2:**</span>
>
> Try finding the frequency relationship between operations(usually try find whether #A<#B or B is rare but expensive and the cost of B is less than sum of previous A)

> 📔 <span style="color:#3333ff">**note:**</span>
>
> When the cost and frequency of some special expensive operations are easy to count, it's easy to use aggregate method. For accounting method, if there is dependency of number of operations(especially when the expensive operation is proved to be less frequent than the cheap operaion, then can pay extra coin for cheap operation for expensive operation)







#### 2. Queues

A queue structure that supporting the following two operations:

-  INSERT: insert one element in O(1)
- EMPTY: empty the queue

Analysis of time complexity: the empty is a sequence of DELETE operation, where the number of delete equals to the number of elements in the queue. Moreover. it's assumed that DELETE is O(1) operation.

##### Aggregation method

​	**Observation**: The number of DELETE is less than the number of INSERT at any time

​	From the Observation we can claim that If there are k INSERT in the operation sequence, the sum of cost 	of all EMPTY will be $\leq$  k

​	Hence the total cost is $O(2k)=O(k)$, and the average cost of each operation is O(1)

##### 

##### Accounting method

​	Define the amortized cost of operation as follows:

  - INSERT: 2

  - EMPTY: 0 

    (Whenever insert, we pay extra 1, which is used to pay the empty operation later)

 TOTAL_COST = 2 * #INSERT = $\leq 2n$



##### Potential method

​	Define the potential function as follows:

- $\phi(0)=0$

- $\phi(i)$: the number of elements in the queue after i operations

Because the number of elements in the queue is never negative, hence $\phi(i)\geq \phi(0)$

- INSERT: $c_i = t_i+\phi(i)-\phi(i-1)=1+i-(i-1)=2$
- EMPTY: $c_i = t_i+\phi(i)-\phi(i-1)= \phi(i-1)+0-\phi(i-1)=0$



#### 3. Dynamic table(vector in C++)

The size of array may not be known in advance, when the initial array is full, we should allocate more memory space. One way is to double the size of the array whenever it's ful.

Notation:

- n: number of element in the current state of table
- createTable(k): a system call that create a table of size k and return its pointer
- size(T): the size of table T
- copy(T,T'): copy the contents of Table T into T'
- free(T): free the space occupied by table T

Further explaination: RTBD(for review purpose ):

1. Try discuss the time complexity of the data structure with aggregate method, accountign method and potential method respectively.

## Philip Bille & Inge Li Gørtz
### Reading
- *Introduction to Algorithms*, 4th edition, Cormen, Rivest, Leiserson, and Stein (CLRS): Chapter 3.
---
## Exercises
### 1. Asymptotic Growth
Arrange the following functions in increasing asymptotic order, i.e., if $f(n)$ precedes $g(n)$, then $f(n) = O(g(n))$.

- $n$
- $n\log n$
- $n^2$
- $2^n$
- $n^3$
#### Answer
$$
\sqrt{n},n,n\log n,n^2,n^3,2^n
$$
### 2. $\Theta$-notation

Write the following expressions using $\Theta$-notation:
- $n^2 + n^3/2$ : $\Theta(n^2)$

- $2^n + n^4$ : $\Theta(2^n)$

- $\log_2 n + n\sqrt{n}$ :  $\Theta(n\sqrt{n})$

- $n(n - 6)$ :  $\Theta(n^2)$

* $4\sqrt{n}$ : $\Theta(\sqrt{n})$

- $8\log_2^7 n + 34\log_2 n + \frac{1}{1000} n$ : $\Theta(n)$

- $2^n7 + 5\log_2^3 n$ : $\Theta(2^n)$

- $n(n^2 - 18) \log_2 n$ : $\Theta(n^3\log_2 n)$

- $n\log_2^4 n + n^2$ : $\Theta(n^2)$

- $n^3\log_2 n + \sqrt{n}\log_2 n$ :  $\Theta(n^3\log_2 n)$
### 3. Loopy Loops
Analyze the running time of the following loops as a function of $n$ and express the result in $O$-notation.
#### LOOP1(n)

```pseudo
i = 1
while i ≤ n do
    print "*"
    i = 2 * i
end while
```
As $i$ is doubling each time we can say that the time it follows is $O(\log_2 n)$
#### LOOP2(n)

```pseudo
i = 1
while i ≤ n do
    print "*"
    i = 5 * i
end while
```
As $i$ is increasing by five times each time we can say that the time it follows is $O(\log_5 n)$
#### LOOP3(n)

```pseudo
for i = 1 to n do
    j = 1
    while j ≤ n do
        print "*"
        j = 2 * j
    end while
end for
```
the first loop has a time complexity of $O(n)$ and the while statement has a complexity of $O(\log_2 n)$ so the complexity is $O(n) \cdot O(\log_2 n) = O(n\log_2 n)$.
### 4. Asymptotic Statements

Which of the following statements are true?
- $\frac{1}{20} n^2 + 100n^3 = O(n^2)$ : False

- $\log_2 n + n = O(n)$ : True

- $2^{\log_2 n} = O(n)$ : True

- $\frac{n^3(n - 1)}{5} = \Theta(n^3)$ : False

- $\log_2^2 n + n = \Theta(n)$ : True

- $\frac{n^3}{1000} + n + 100 = \Omega(n^2)$ : True

- $2^n + n^2 = \Omega(n)$ : True

- $\log_4 n + \log_{16} n = \Theta(\log n)$ : True

- $n^{1/4} + n^2 = \Theta(n)$ : False 

- $2^{\log_4 n} = \Theta(\sqrt{n})$ : True
### 5. Doubling Hypothesis
#### 5.1 $[w]$
Algorithm A runs in exactly $7n^3$ time on an input of size $n$. How much slower does it run if the input size is doubled?
$$
7(2n)^3 = 7\cdot 8n^3 = 56n^3 
$$
So it takes 8 times more.
#### 5.2
Algorithm B runs in time respectively 5, 20, 45, 80, and 125 seconds on inputs of sizes 1000, 2000, 3000, 4000, and 5000. Give an estimate of the running time of B on a input of size 6000. Express the (estimated) running time of B using O-notation as a function of the input size n.
![[Pasted image 20250226140344.png]]
This makes sense as we see that each time the values increase by more and more. 
#### 5.3
Algorithm C runs 3 seconds slower each time the size of the input is doubled. Express the running time of C in $O$-notation.
As we double each time we can say it follows something that will increase by 3 seconds each time, we can express this as $3 \log_2 n = O(\log n)$.
### 6. Asymptotic Properties
#### 6.1
Let $f(n)$ and $g(n)$ be asymptotically non-negative. Show that $\max(f(n), g(n)) = \Theta(f(n) + g(n))$.
#### Answer
By definition, the maximum function satisfies:
$$
\max(f(n), g(n)) \leq f(n) + g(n)
$$
this means that there must exists a constant $c_1 = 1$ such that
$$
	\max(f(n), g(n)) \leq c_1(f(n) + g(n))
$$
for all sufficiently large $n$. This establishes the upper bound.

Since $\max(f(n), g(n))$ is always at least as large as either $f(n)$ or $g(n)$, we have:
$$
\max(f(n),g(n)) \geq \frac{1}{2}(f(n) + g(n))
$$
This establishes the lower bound, where $c_2 = \frac{1}{2}$. Since we have established both:
$$
c_1(f(n) + g(n)) \geq \max(f(n),g(n)) \geq \frac{1}{2}(f(n) + g(n))
$$
#### 6.2
Explain why the statement "the running time of algorithm A is at least $O(n^2)$" does not make sense.
This does not make sense as $O(n^2)$ says that the running time can be lower, but cannot be higher. 
#### 6.3
Is $2^{n+1} = O(2^n)$? Is $2^{2n} = O(2^n)$? : Yes and no

#### 6.4
Show that $\log_2(n!) = O(n \log n)$.

#### 6.5 $[*]$
Show that $\log_2(n!) = \Omega(n \log n)$ and conclude that $\log_2(n!) = \Theta(n \log n)$.

### 7. Generalized Merge Sort

  

Professor M. Erge suggests a variant of merge sort called **3-merge sort** that splits the array into 3 parts instead of 2.

  

#### 7.1

Show that it is possible to merge 3 sorted arrays in linear time.

  

#### 7.2

Analyze the running time of 3-merge sort.

  

#### 7.3 $$*$$

Generalize the algorithm and the analysis of 3-merge sort to **k-merge sort** for $k > 3$. Is **k-merge sort** an improvement over the standard 2-merge sort?

  

### 8. Maximal Subarray

  

Let $A[0..n−1]$ be an array of integers (both positive and negative). A **maximal subarray** of $A$ is a subarray $A[i..j]$ such that the sum $A[i] + A[i+1] + \dots + A[j]$ is maximal among all subarrays of $A$.

  

#### 8.1 $$*w*$$

Give an algorithm that finds a maximal subarray of $A$ in $O(n^3)$ time.

  

#### 8.2 $$*†*$$

Give an algorithm that finds a maximal subarray of $A$ in $O(n^2)$ time. Hint: Show it is possible to compute the sum of any subarray in $O(1)$ time.

  

#### 8.3 $$*†*$$

Give a **divide and conquer** algorithm that finds a maximal subarray of $A$ in $O(n \log n)$ time.

  

#### 8.4 $$*∗∗*$$

Give an algorithm that finds a maximal subarray of $A$ in $O(n)$ time.
Euclid's Algorithm returns the greatest common divisor of two input numbers. 

In pseudocode:
``` Pseudocode
Require: integers a and b
Wlog, suppose a >= b
Set r(0) = a, r(1) = b, i = 1
while r(i) != 0 do
	i <- i + 1
	Compute unique integers  m(i) and r(i) such that 0 <= r(i) <= r(i-1) and r(i-2) = m(i) * r(i-1) + r(i)
return r(i)
```
The second step in the loop is division with remainder - essentially divide `r(i-2)` by `r(i-1)` and set the remainder as `r(i)`.
# Euclid's Corollary
Euclid's Corollary can be stated as follows: Let $a$ and $b$ be integers. Let $d = \text{GCD}(a,b)$ then there exists $m,n \in \Bbb Z$ such that $am + bn = d$.
The series $\{r_{i-2} = m_i \times r_{i-1} + r_i\}_{2 \le i \le k}$ arises from Euclid's Algorithm. 
Let $a=r_0$, and $b = r_1$ as done in Euclid's Algorithm. Compute the series via the algorithm. Let $d= r_k$. Expand $r_k$ by continual series substitution until expressed as coefficients of $r_0$ and $r_1$. The coefficients give $m$ and $n$.

#algorithms
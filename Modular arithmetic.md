Modular arithmetic describes the process of arithmetic (using $+,-,\times,\div$ operators) on modular numbers. 
A modular number system of a modulus $m$ defines a [[relation#Congruence relation|congruence relation]] on the [[ring]] of the reals such that $\exists k \in \mathbb Z \text{ s.t. } a = km + b \implies a \equiv b$
If $b$ is minimised then $a \equiv b \pmod m$, and $a \bmod m = b$

# Inverses
Given an $a \in \mathbb Z$ and $n \in \Bbb Z _{>1}$, if there exists $b \in \Bbb Z \ \text{s.t.} \ ab \equiv 1 \pmod n$ then $b \pmod n$ is the inverse of $a \pmod n$. 
Inverses are not guaranteed to exist (hence why modular numbers define a ring, not a group). For instance, $a=5,n=10$, $5 \times 2 \bmod {10} = 0$, and so $5 \times k \bmod 10$  can only ever yield $5$ or $0$. 
In general, $a \pmod n$ has an inverse if $a$ and $n$ are coprime. 

Computing inverses can be done via [[Euclid's Algorithm#Euclid's Corollary|Euclid's corollary]]. This corollary gives, and constructs, integers $m,n$ such that $am + bn = d$. 
Given the task of finding the inverse of $x \pmod k$, set $a = k$, and $b=x$, to yield values $m,n$ such that $km + bn = 1$, since $d$ is the greatest common divisor, and (for an inverse to exist) $x$ and $k$ must be coprime. 
$(km + bn) = 1 \pmod k$, so $bn = 1 \pmod k$, $n$ is the inverse of $b$, $b=x$, so $n \pmod k$ is the inverse of $x \pmod k$.

# Groups
The set $\{0 \pmod p, 1 \pmod p, \dots, p-1 \pmod p\}$ is expressed $\Bbb Z / p \Bbb Z$.
Given $p$ is a prime (to ensure coprime values giving inverses), the set $\{1 \pmod p, 2 \pmod p, \dots, \}$ is a [[group]] under multiplication, as every value has an inverse. This group can be expressed $(\Bbb Z / p \Bbb Z)^*$, where $X^*$ means $X \setminus \{0\}$. 
Further, $(\Bbb Z / p \Bbb Z)^*$ is a [[group#Cyclic groups|cyclic group]].  

#discrete-maths

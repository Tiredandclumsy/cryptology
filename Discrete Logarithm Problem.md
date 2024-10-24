The Discrete Logarithm Problem (DLP) describes obtaining a power used in a given exponential in [[modular arithmetic]]: obtaining $n$ from $p, g, g^n \pmod p$. 

It is required for this to be exponential in $\lambda$ where $\lambda = \log _2 p$ for [[Diffie-Hellman Key Exchange]] to be secure.

This problem can be solved by the [[Pohlig-Hellman algorithm]].
# Solving DLP
If $g$ is a generator of $(\Bbb Z / p \Bbb Z)^*$, it has [[group#Order|order]] $p-1$ from [[Fermat's Little Theorem]]. Further, if $\ell$ divides $p-1$ then $g^{\frac{p-1}{\ell}}\pmod p$ has order $\ell$. #incomplete prove this
This gives a way of finding elements of a given order.
#incomplete add method of solving DLP

#cryptology
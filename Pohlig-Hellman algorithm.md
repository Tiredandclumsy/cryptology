The Pohlig-Hellman algorithm is a method to solve the [[Discrete Logarithm Problem]] - given a prime $p$, a $g \in (\Bbb Z \ p \Bbb Z)^*$ of [[group#Order|order]] $p-1$ ($g$ is a generator), and $g^a \pmod p$, find $a$.

By [[Fermat's Little Theorem]], $\forall k \in \Bbb Z. g^{a + (p-1)k} = g^a g^{(p-1)k}\equiv g^a \pmod p$.
Thus it suffices to find $a \pmod{p-1}$. 
First, factorise $p-1 = q_1 ^{e_1} \times q_2^{e_2} \times \dots \times q_r ^{e_r}$ into prime factors
For each $i = 1, \dots, r$
- Express the goal $a = a_0 + a_1q_i + a_2q_1^2 + \dots$ where $a_j \in [0,q_i - 1]$
- Compute $a_0 = a \pmod{q_i}$
#incomplete explain PH


#cryptology
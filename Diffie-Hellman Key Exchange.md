Diffie-Hellman Key Exchange is a simple mode of [[key exchange]]. The procedure, given two actors A and B, is as follows:
- Let $p$ be a publicly chosen prime number.
- Let $G=((\Bbb Z / p \Bbb Z), \times)$ be the [[Modular arithmetic#Groups|modular group]] of $\bmod p$
- Let $g$ be a generator of $G$
- A chooses a number $a \bmod p$, and shares the public key $g^a \bmod p$
- B chooses a number $b \bmod p$, and shares the public key $g^b \bmod p$
- The shared secret $ss = g^{ab} \bmod p$, computed by A as $(g^b)^a \bmod p$, and computed by B as $(g^a)^b \bmod p$

$g$ being a generator is important - it gives $p-1$ possible values of the [[Discrete Logarithm Problem]] when trying to maliciously calculate the shared secret. This also means there is only 1 valid private key $d$ for every public key $g^d$.

In order for this process to be useful however, it must be 'hard' (in some usefully defined way) to gain the shared secret from the public communication. Given a security parameter $\lambda = \log _2 p$, exponentiation $\bmod p$ is polynomial in $\lambda$, and the [[Discrete Logarithm Problem]] is subexponential in $\lambda$.


#cryptology
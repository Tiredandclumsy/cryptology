RSA is a public key encryption scheme. The procedure of a person $A$ receiving a message from a person $B$ is as follows:
Key Generation:
- $A$ picks secret primes $p \ne q$ of public it length $\lambda$
- $A$ computes the public value $n = p \times q$ and private value $\varphi(n) = (p-1)(q-1)$ (where $\varphi$ is the [[Euler Phi-Function]])
- $A$ picks a public $e$ coprime to $\varphi(n)$
- $A$ computes private value $d = e^{-1} \pmod{\varphi(n)}$
- The public key is then $pk = (e,n)$ and the private key is $sk = (d,n)$
- $A$ sends $pk$ to $B$
Encryption:
- $B$ picks $m \in \Bbb Z, 0 \le m \le n-1$
- $B$ computes $c = m^e \pmod n$
- $B$ sends $c$ to $A$
Decryption
- $A$ computes $m \pmod n = c^d \pmod n$

# Validity
In order for RSA to be a valid system, the existence of $e^{-1}$ in key generation step 4 and the correctness of decryption must be proven, as they are not trivially correct.
It can be proven that $e$ is invertible, as $a \bmod b$ is invertible iff. $a$ and $b$ are coprime. This criterion is stated in key generation step 3, and so key generation is valid.
To prove correctness, it can be noted that if $m$ is invertible $\bmod n$ then [[Fermat's Little Theorem]] implies $m^{\varphi (n)} \equiv 1 \pmod n$. Let $k \in \Bbb Z$ be such that $ed = 1 + k \varphi(n)$, in other words $k = \cfrac {ed -1}{\varphi(n)}$
$c^d = (m^e)^d = m^{1 + k \varphi(n)} = m \left(m^{\varphi(n)}\right)^k = m \times 1^k = m \pmod n$

# Practicality
For RSA to be practical as a crypto-system, a few things must hold.
- Key generation step 2 (computing $\varphi(n)$) must be polynomial
- Key generation step 4 (computing inverse $\pmod{\varphi(n)}$) must be polynomial 
- Recovering $d$ from $(e,n)$ should be sub-exponential, which requires recovering $n$ from $\varphi(n)$ and factorising $n$ to be sub-exponential
- Step 2 of encryption (exponentiation $\bmod n$) should be polynomial
- $m$ should not be recoverable from $c$, which requires $e$th roots $\bmod n$ should be sub-exponential
Fast multiplication is done via [[double-and-add]]. 
#incomplete add analysis
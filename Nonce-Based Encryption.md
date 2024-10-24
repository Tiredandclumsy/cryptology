Nonce-Based Encryption describes a method of encoding multiple blocks of information while preventing any repeated encryption. This is done with a nonce - a value unique to a single instance of encryption. 
Formally, a nonce-based encryption scheme is a system of 3 algorithms $(K_g, E, D)$ given a key space $\mathcal K$, a space to sample the nonce from $\mathcal N$, a message space $\mathcal M$, and a cipher space $\mathcal C$, assuming $\mathcal M = \mathcal C$ where:
- $K_g \rightarrow k \in K$
- $E(k,n,m) = E_k^n(m) \rightarrow c \in \mathcal C$
- $D(k,n,c) = D_k^n(c) \rightarrow m' \in \mathcal M$ 
A nonce-based encryption scheme is 'correct' if $\forall k \in \mathcal K, m \in \mathcal M, n \in \mathcal N. D_k^n \left(E_k^n \left(m \right)\right) = m$

An encryption scheme being nonce-based allows additional control over the ciphertext. Usually, a [[blockcipher]] is nonce-based, allowing the prevention of the same block giving the same ciphertext.

[[Security#Indistinguishability#Oracle-based indistinguishability|Indistinguishability]] for nonce-based encryption is identical to standard indistinguishability, but the oracle is either randomly sampling from the ciphertext, or encrypting with the key a new unique nonce. This constraint removes the requirement that the adversary needs to make unique queries to the oracle. 

#cryptology
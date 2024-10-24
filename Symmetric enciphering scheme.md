A symmetric enciphering scheme is a system of 3 algorithms $(K_g, E, D)$ given a key space $\mathcal K$, a message space $\mathcal M$, and a cipher space $\mathcal C$, assuming $\mathcal M = \mathcal C$ where:
- $K_g \rightarrow k \in K$
- $E(k,m) = E_k(m) \rightarrow c \in \mathcal C$
- $D(k,c) = D_k(c) \rightarrow m' \in \mathcal M$
A symmetric enciphering scheme is 'correct' if $\forall k \in \mathcal K, m \in \mathcal M. D_k(E_k(m)) = m$

#cryptology 
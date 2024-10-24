One-time pad is a simple [[symmetric enciphering scheme]] where $\mathcal K = \mathcal M = \mathcal C = \{0,1\}^\ell$. 
It is defined as:
$\begin{aligned} & K_g() \\ \hline & k \leftarrow _\$ \{0,1\}^\ell \\ & \text{return} \ k \end{aligned}$ $\begin{aligned} & E_k(m) \\ \hline & c \leftarrow m \oplus k \\ & \text{return} \ c \end{aligned}$ $\begin{aligned} & D_k(c) \\ \hline & m \leftarrow c \oplus k \\ & \text{return} \ m \end{aligned}$
where $\oplus$ means bitwise xor.

#cryptology
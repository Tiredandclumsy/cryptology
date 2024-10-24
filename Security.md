# Perfect secrecy
Perfect secrecy of an encryption scheme means an attacker cannot recover the message from a given ciphertext. 
Formally: $\forall c \in \mathcal C, m \in \mathcal M. \text{Pr}(m^* = m | c^* = c) = \text{Pr}(m^* = m)$
where $k \leftarrow_\$ K_g, m^* \leftarrow _\$ \mathcal M, c^* = E_k(m^*)$
[[One-Time Pad]] is the only perfectly secret [[Symmetric enciphering scheme|enciphering scheme]] up to [[isomorphism]]. 
# Indistinguishability
Perfect secrecy, when defined as a [[security experiment]] gives rise to indistinguishability.

Indistinguishability of an [[Symmetric enciphering scheme|enciphering scheme]] is the inability of an adversary to distinguish between a random ciphertext and an encryption of a given plaintext. 
For 1-time indistinguishability:
$\begin{aligned} & \text{Exp} _E ^{\text{1ind-real}} (\Bbb A) \\ \hline & k \leftarrow_\$ K_g \\ & m \leftarrow_\$ \Bbb A \\ & c^* \leftarrow E_k(m) \\ & \hat b \leftarrow_\$ \Bbb A(c^*) \end{aligned}$ $\begin{aligned} & \text{Exp}_E^{\text{1ind-ideal}}(\Bbb A) \\ \hline & k \leftarrow_\$ K_g \\ & m \leftarrow_\$ \Bbb A \\ & c^* \leftarrow_\$ \mathcal C \\ &\hat b \leftarrow _\$ \Bbb A(c^*) \end{aligned}$
$$\text{Adv}_E^{\text{1ind}}(\Bbb A) = \text{Pr}\left( \text{Exp}_E^{\text{1ind-real}} (\Bbb A):\hat b = 1 \right) - \text{Pr} \left( \text{Exp}_E ^{\text{1ind-real}}(\Bbb A) : \hat b = 1 \right)$$
An enciphering scheme $E$ is perfectly indistinguishable if for every algorithm $\Bbb A$, $\text{Adv}_E ^{\text{1ind}}(\Bbb A) = 0$
To weaken this definition, the adversary's resources can be limited, or a certain error of advantage can be permitted. Thus, an enciphering scheme $E$ is $(t,\epsilon)$-indistinguishable if for every $\Bbb A$ that runs in time at most $t$, $\text{Adv}_E ^{\text{1ind}}(\Bbb A) \le \epsilon$.

## Oracle-based indistinguishability
Further, the algorithm can be given an [[oracle]] that either implements the encryption for a fixed key, or gives a random plaintext. Then the algorithm can query the oracle a number of times, assuming it cannot query the same plaintext twice, and using the resulting information it can return which oracle it was given.
$\begin{aligned} & \text{Exp}_E^{\text{ind-real}}(\Bbb A) \\ \hline & k^* \leftarrow_\$ K_g \\ & \hat b \leftarrow _\$ \Bbb A^{\mathcal E} \\ \hdashline & \mathcal E(m) \\ \hline & \text{no repeat queries} \\ & c \leftarrow E_{k^*} (m) \\ & \text{return} \ c \end{aligned}$    $\begin{aligned} & \text{Exp}_E^{\text{ind-ideal}}(\Bbb A) \\ \hline & \hat b \leftarrow _\$ \Bbb A^{\mathcal E} \\ & \\ \hdashline & \mathcal E(m) \\ \hline & \text{no repeat queries} \\ & c \leftarrow_\$ \mathcal C \\ & \text{return} \ c \end{aligned}$
$$\text{Adv}_E^{\text{ind}}(\Bbb A) = \text{Pr}\left( \text{Exp}_E^{\text{ind-real}}(\Bbb A) : \hat b = 1 \right) - \text{Pr}\left( \text{Exp}_E^{\text{ind-ideal}}(\Bbb A): \hat b = 1 \right)$$
The requirement to disallow repeated queries is to avoid  an obvious distinguishing attack - the same query made twice will always return the same enciphered ciphertext, but will return the same random ciphertext with a probability $\frac 1 {|\mathcal C |}$

This requirement is removed when testing indistinguishability of [[nonce-based encryption]].
## Pseudorandomness
Indistinguishability of a [[blockcipher]] is known as pseudorandomness. 
The same rules apply, in that $(t,q,\epsilon)$-pseudorandomness is equivalent to $(t,q,\epsilon)$-indistinguishability.


#cryptology
Key recovery is a notion of security in cryptology, expressing the ability of an attacker to find the key used in a particular instance of encryption.

# Passive key-recovery
The simplest mode of key recovery is passive. It can be defined by a [[security experiment]] and an [[adversarial advantage]]:
Let $E$ be an enciphering scheme.
$\begin{aligned} & \text{Exp}_E ^\text{kr-pas} (\Bbb A) \\ \hline & k^* \leftarrow _\$ K_g \\ & \hat k \leftarrow _\$ \Bbb A \end{aligned}$ 
The advantage of $\Bbb A$ in passively recovering the key is defined as $\text{Adv}_E ^{\text{kr-pas}}(\Bbb A) = \text{Pr} \left( \text{Exp} _E ^{\text{kr-pas}}(\Bbb A) : \hat k = k^* \right)$ meaning the probability $\Bbb A$ gives the correct key.
In other words, passive key recovery evaluates the ability of an adversary to give the key used in a particular encryption without any knowledge of the encryption itself.
The best an adversary can do in this case is guess: $\Bbb A_{\text{guess}}$ can be defined $$\begin{aligned} & \Bbb A_{\text{guess}} \\ \hline & \hat K \leftarrow_\$ K_g \\ & \text{return} \ \hat k \end{aligned}$$This adversary has an advantage $\text{Adv} _E ^{\text{kr-pas}}(\Bbb A_{\text{guess}}) = \cfrac 1 {|\mathcal K|}$
# Chosen plaintext
Another experiment measuring key recovery permits the adversary [[Oracle]] access to $E_k$ for a fixed $k \leftarrow K_g$. This adversary can then strategically give plaintexts to the oracle, and use the resulting ciphertext to inform the key recovery.
$\begin{aligned} & \text{Exp}_E ^{\text{kr-cpa}}(\Bbb A) \\ \hline & k^* \leftarrow_\$ K_g \\ & \hat k \leftarrow_\$ \Bbb A ^ \mathcal E \end{aligned}$    $\begin{aligned} & \mathcal E(m) \\ \hline & c \leftarrow E_{k^*}(m) \\ & \text{return} \ c \end{aligned}$
$$\text{Adv}_E ^{\text{kr-cpa}}(\Bbb A) = \text{Pr} \left( \text{Exp}_E^{\text{kr-cpa}}(\Bbb A) : \hat k = k^* \right)$$

An enciphering scheme $E$ is $(t,q,\epsilon)$-secure against chosen plaintext key recovery if for every algorithm $\Bbb A$ running in at most time $t$ and making $q$ queries to its oracle, $\text{Adv}_E^{\text{kr-cpa}}(\Bbb A) \le \epsilon$.

Given just once instance of this oracle search ($q-1$), the best algorithm for advantage is exhaustive search:
$\begin{aligned} & \Bbb A_{\text{search}} \\ \hline & K_s \leftarrow \emptyset \\ & m \leftarrow_\$ \mathcal M \\ & c \leftarrow \mathcal E(m) \\ & \text{for} \ k \in \mathcal K \\ & \quad \text{if} \ E_k(m) = c \\ & \quad \text{then} \ K_s \leftarrow K_s \cup \{k\} \\ & \hat k \leftarrow_\$ K_s \\ & \text{return} \ \hat k \end{aligned}$
This is often used as a baseline metric of block cipher security. When an algorithm is found that is significantly better (less costly) than exhaustive search, the enciphering is considered broken. 
This gives rise to a standard measure of security for block ciphers: $n$-bit security means breaking the cipher should be as costly as running $2^n$ rounds of encryption.

Lightweight cryptology is 112 bit, and is admissible in extreme circumstances. 128 bit security is good for short term transfer, and 256 bit is the minimum for long term data storage.

The metric of [[Security#Indistinguishability|inidstinguishability]] for blockciphers is called pseudorandomness. 

#cryptology
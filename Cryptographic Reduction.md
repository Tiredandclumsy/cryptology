When reasoning about cryptographic systems, it is often useful to define a notion of strength between adversary powers. This is done by means of reduction.
A cryptographic reduction from $\Bbb B \to \Bbb A$ is a proof that, given an adversary $\Bbb A$ of a given power $\text{power}_1$, an adversary $\Bbb B$ on power $\text{power}_2$ can be constructed using $\Bbb A$ as a subroutine such that $\text{Adv} _E ^{\text{power}_1}(\Bbb A) \le \text{Adv}_E ^{\text{power}_2}(\Bbb B)$, where $\Bbb B$ has the same order of runtime as $\Bbb A$. 
In other words, $\Bbb B$ can be solved in linear time using a constant time oracle that solves $\Bbb A$.

In general, by reductions, $\text{kr-1cpa}$ is at least as easy as  $\text{kr-1kpa}$, which is at least as easy as KR-1KCA. $\text{ow-pas}$ is also at least as easy as KR-1KCA, and that is at least as easy as KR-PAS. If KR-PAS is insecure then all the other powers are trivially insecure, and the passively gained key can be used to encrypt or decrypt any given information.

# $\text{kr-1cpa}$ to $\text{kr-1kpa}$
A simple reduction is that from a one time chosen ciphertext attack to a one-time known ciphertext attack, that is $\text{kr-1kpa}$ is no easier than $\text{kr-1cpa}$. 
This can be done by 'choosing' a random plaintext, then feeding it to the known plaintext oracle. 
$\begin{aligned} & \text{Exp} _E ^{\text{kr-1cpa}} (\Bbb B _{\text{kr-1cpa}})\\ \hline & k^* \leftarrow_\$ K_g \\ & \hat k \leftarrow_\$ \Bbb B_{\text{kr-1cpa}} ^{\mathcal E _{\text{cpa}}}(k^*)\end{aligned}$    $\begin{aligned} & \Bbb B_{\text{kr-1cpa}} ^{\mathcal E _{\text{cpa}}} \\ \hline & \hat k \leftarrow_\$ \Bbb A _\text{kr-1kpa} ^{\mathcal E_{cpa}} \\ & \text{return} \ \hat k \end{aligned}$    $\begin{aligned} & \mathcal E_{\text{kpa}} \\ \hline & m \leftarrow_\$ \mathcal M \\ & c \leftarrow \mathcal E_{\text{cpa}} (m) \\ & \text{return} \ (m,c) \end{aligned}$    $\begin{aligned} & \mathcal E_{\text{cpa}}(m) \\ \hline & c \leftarrow E_{k^*}(m) \\ & \text{return} \ c \end{aligned}$
Here $\Bbb B$ is an adversary that solves for $\text{kr-1cpa}$, and uses an assumed oracle $\Bbb A$ that solves $\text{kr-1kpa}$. Note the oracle used by $\Bbb A$ is simply the oracle used in the known ciphertext experiment. 
# $\text{ow-pas}$ to $\text{kr-1kca}$
$\text{ow-pas}$ can be reduced to $\text{kr-1kca}$ by simply using the recovered key to decrypt the ciphertext. 
#incomplete add syntax of this reduction
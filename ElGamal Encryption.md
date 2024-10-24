ElGamal Encryption is an [[Asymmetric enciphering scheme]] that uses [[Diffie-Hellman Key Exchange]] and [[One-Time Pad]] to encrypt messages.

The procedure, assuming a person $A$ receiving an encrypted message sent by a person $B$, is as follows:
Setup
- $A$ chooses a prime $p$ and a generator $g$ of $(\Bbb Z / p \Bbb Z)^*$
- $A$ chooses a random secret $a \in \{0,\dots,p-1\}$ and computes $pk_A = g^d \pmod p$
- $A$ sends the public key $(p,g,pk_A)$ to $B$
Encryption
- $B$ chooses a random secret $b \in \{1,\dots,p-1\}$ and computes $pk_B = g^b \pmod p$
- $B$ computes the shared secret $ss = {pk_A}^b \pmod p$
- $B$ encrypts the message $c = m \times ss$
- $B$ sends the ciphertext $(pk_B, c)$ to $A$
Decryption
- $A$ computes the shared secret $ss = {pk_B}^a \pmod p$
- $A$ computes the multiplicative inverse of the secret $ss^{-1} = {pk_B}^{p-1-d} \pmod p$
- $A$ decrypts the ciphertext $m = c \times ss^{-1}$

The inverse shared secret can be calculated as ${pk_B}^{p - 1 - d}$ because $ss \times {pk_B}^{p - 1 - d} = g^{ab} \times {g^b}^{p - 1 - d} = \left( g^{p-1} \right)^h = 1 \pmod p$
If $m$ is known then $ss$ can be recovered from $c$, so a new secret $b$ must be used for each message.

#cryptology 
Modes of Operation are methods by which a [[blockcipher]] can be used to encrypt an arbitrary size of plaintext. 

# ECB
ECB (Electronic Codebook) is the most simple mode of operation. Given a block cipher of block length $\ell$, it takes every $\ell$-length block of the plaintext, encrypts in via the blockcipher, and then concatenates the ciphertexts into a single ciphertext output. 
ECB is never used in practice, as it encrypts identical blocks of plaintext into identical blocks of ciphertext, allowing patterns in the plaintext to remain when encrypted.

# CTR
Counter Mode (CTR) fixes the issue with ECB of identical blocks by introducing a [[Nonce-Based Encryption|nonce-based]] blockcipher. Every block is then given an index, which is passed (usually via a counter function) as the nonce to the cipher.

# CBC
Cipher Block Chaining Mode (CBC) has two versions: it either XORs the previous ciphertext block with the next plaintext block before it is encrypted, or XORs the previous plaintext with the next ciphertext after encryption, again preventing the repeated block encryption problem of ECB.

#cryptology
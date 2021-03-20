# Reading

[Ceasar Cipher](https://en.wikipedia.org/wiki/Caesar_cipher)

Caesar cipher: In cryptography, a Caesar cipher, also known as Caesar's cipher, the shift cipher, Caesar's code or Caesar shift, is one of the simplest and most widely known encryption techniques. It is a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet. For example, with a left shift of 3, D would be replaced by A, E would become B, and so on. The method is named after Julius Caesar, who used it in his private correspondence.[1]

Diffie-Herman Key Exchange: [Reference](https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange)
It is a method of securely exchanging cryptographic keys over a public channel and was one of the first public-key protocols as conceived by Ralph Merkle and named after Whitfield Diffie and Martin Hellman.DH is one of the earliest practical examples of public key exchange implemented within the field of cryptography.

## Videos

[Cryptography Crash Course](https://www.youtube.com/watch?v=jhXCTbFnK8o)

## Additional Resources

[Introduction to Cryptography](https://thebestvpn.com/cryptography/)

# Cryptography

Cryptography, at its most fundamental level, requires two steps: encryption and decryption. The encryption process uses a cipher in order to encrypt plaintext and turn it into ciphertext. Decryption, on the other hand, applies that same cipher to turn the ciphertext back into plaintext.

- Plain: ABCDEFGHIJKLMNOPQRSTUVWXYZ

- Cipher: XYZABCDEFGHIJKLMNOPQRSTUVW

**Obfuscation** is defined as “The act of making something unclear, obscure, or unintelligible”. It means that, in order to transmit a secure message, you must hold back some of the information required to understand the message.

With **cryptography**, a specific key and numerous calculations are required. Even if someone knew the encryption method used, they wouldn’t be able to decrypt the message without the corresponding key, making your information much more secure.

**1. Hashing**

Hashing is a type of cryptography that changes a message into an unreadable string of text for the purpose of verifying the message’s contents, not hiding the message itself.

**2. Symmetric Cryptography**

Symmetric Cryptography, likely the most traditional form of cryptography, is also the system with which you are probably most familiar. This type of cryptography uses a single key to encrypt a message and then decrypt that message upon delivery.

**3. Asymmetric Cryptography**

*Asymmetric Encryption: [Reference](https://en.wikipedia.org/wiki/Public-key_cryptography)

Asymmetric cryptography (as the name suggests) uses two different keys for encryption and decryption, as opposed to the single key used in symmetric cryptography.

The first key is a public key used to encrypt a message, and the second is a private key which is used to decrypt them. The great part about this system is that only the private key can be used to decrypt encrypted messages sent from a public key.

**The 4 Types of Cryptographic Functions**

1.Authentication

2.Nonrepudiation

3.Confidentiality

4.Integrity


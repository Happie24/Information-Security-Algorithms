# Cryptography Algorithms in Python

This repository contains Python implementations of various cryptography algorithms, including AES, DES, A5/1 stream cipher, Diffie-Hellman key exchange, transposition cipher, and more. Each algorithm comes with a brief description and example usage.

## Table of Contents
- [Shift-BY-N Cipher](https://github.com/PragatiDBhat/Information-Security-Algorithms/blob/main/Shift%20By%20N%20Cipher.md)
- [Playfair Cipher](https://github.com/PragatiDBhat/Information-Security-Algorithms/blob/main/Playfair%20Cipher.md)
- [Hill Cipher](https://github.com/PragatiDBhat/Information-Security-Algorithms/blob/main/Hill%20Cipher.md)
- [Transposition Cipher](https://github.com/PragatiDBhat/Information-Security-Algorithms/blob/main/TranspositionCipher.md)
- [Diffie-Hellman Key Exchange](https://github.com/PragatiDBhat/Information-Security-Algorithms/blob/main/Deffie-Hellman.md)
- [AES Encryption](https://github.com/PragatiDBhat/Information-Security-Algorithms/blob/main/AES.md)
- [DES Encryption](https://github.com/PragatiDBhat/Information-Security-Algorithms/blob/main/DES.md)
- [A5/1 Stream Cipher](https://github.com/PragatiDBhat/Information-Security-Algorithms/blob/main/A5-1.md)


### 1. **Shift By n (Caesar Cipher)**
The Shift By n, or Caesar Cipher, is a simple substitution cipher where each letter in the plaintext is shifted by a fixed number of places down the alphabet. For example, with a shift of 3, 'A' becomes 'D', 'B' becomes 'E', and so on. This algorithm is easy to implement and decode but offers minimal security since it can be easily broken using frequency analysis.

### 2. **Transposition Cipher**
In a transposition cipher, the positions of the letters in the plaintext are shifted according to a regular system to form the ciphertext. Unlike substitution ciphers, the actual letters are not changed; rather, their order is altered. For example, if the keyword is “ZEBRA,” the plaintext might be rearranged based on the order of letters in the keyword. This method can provide better security than simple substitution ciphers, but it can still be vulnerable to various attacks.

### 3. **Playfair Cipher**
The Playfair Cipher is a digraph substitution cipher that encrypts pairs of letters (digraphs) instead of single letters. A 5x5 grid is created using a keyword or phrase, filling in the letters of the alphabet (excluding 'J', which is typically combined with 'I'). The plaintext is then encrypted based on the position of the letters in the grid. If both letters of a digraph are in the same row or column, they are replaced with the letters to their immediate right or below. This method is more secure than simple substitution ciphers.

### 4. **Hill Cipher**
The Hill Cipher is a polygraphic substitution cipher based on linear algebra. It uses a matrix for encryption and decryption. A block of plaintext (typically a 2x2 or 3x3 matrix) is multiplied by a key matrix to produce the ciphertext. The key matrix must be invertible for decryption. The Hill cipher can encrypt multiple letters at once, making it more complex than traditional ciphers.

### 5. **Diffie-Hellman Key Exchange**
Diffie-Hellman is a method for two parties to securely exchange cryptographic keys over a public channel. It allows them to generate a shared secret key that can be used for subsequent encryption of messages. The algorithm is based on the difficulty of the discrete logarithm problem. Each party selects a private key, computes a public key, and exchanges it. They then use their private key and the other party's public key to compute a shared secret.

### 6. **AES (Advanced Encryption Standard)**
AES is a symmetric encryption algorithm widely used across the globe. It encrypts data in fixed block sizes (128 bits) and supports key sizes of 128, 192, or 256 bits. AES employs a series of transformations, including substitution, permutation, mixing, and key addition, in multiple rounds (10 for 128-bit keys, 12 for 192-bit keys, and 14 for 256-bit keys) to ensure security and efficiency. It's known for its strength and is used in various applications, including file encryption and secure communications.

### 7. **DES (Data Encryption Standard)**
DES is a symmetric-key algorithm that was once a widely used standard for encrypting digital data. It uses a 56-bit key to encrypt data in 64-bit blocks through a series of transformations, including permutations and substitutions across 16 rounds. Although DES was considered secure in its early days, advances in computing power have made it vulnerable to brute-force attacks, leading to its replacement by AES.

### 8. **A5/1**
A5/1 is a stream cipher used for encrypting mobile phone communications (specifically GSM). It operates on 64-bit frames and uses a combination of linear feedback shift registers (LFSRs) to produce a pseudo-random key stream, which is then XORed with the plaintext to create the ciphertext. While A5/1 was considered secure for a time, vulnerabilities have been discovered, making it susceptible to attacks.

These algorithms range from basic ciphers used for educational purposes to robust encryption standards employed in modern secure communications. Each has its own strengths and weaknesses, depending on the context in which it is used.




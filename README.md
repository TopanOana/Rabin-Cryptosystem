# Rabin Cryptosystem Implementation

This project implements the Rabin Cryptosystem, a public-key cryptosystem, in Python. It supports encryption and decryption of messages using a mathematical approach based on modular arithmetic.

## Overview
The Rabin Cryptosystem is based on the difficulty of factoring large integers and offers a unique approach to encryption and decryption, where each ciphertext may correspond to multiple plaintexts. The implementation handles:
- Key generation.
- Message encryption.
- Message decryption.
- Validation of plaintext and ciphertext.

## Features
- **Numerical Equivalent Conversion:**
  - Converts plaintext into numerical equivalents using custom mapping based on block sizes.
- **Encryption:**
  - Transforms plaintext into ciphertext using modular arithmetic.
- **Decryption:**
  - Utilizes the Rabin method to compute the possible plaintext values and determine the correct message.
- **Validation:**
  - Ensures messages contain only valid characters.

## Technical Details
- **Language:** Python
- **Libraries Used:**
  - `math`: For mathematical computations.
  - `sympy`: For prime-checking and least common multiple calculations.
  - `random`: For generating random numbers.

### Key Algorithms
1. **Pollard’s p-1 Algorithm:**
   - Used to factorize numbers during key generation.
2. **Modular Arithmetic:**
   - Efficiently computes modular inverses and solutions for quadratic congruences.
3. **Custom Encoding:**
   - Maps characters to numerical values and back.

## Usage
### Key Generation
Generate a public and private key pair using block sizes for plaintext (`k`) and ciphertext (`l`), ensuring `l > k`.
```python
p, q, key = generate(k, l)
```
### Encryption
Encrypt a plaintext message using the public key.
```python
ciphertext, encrypted_values = encrypt(message, key, k, l)
```
### Decryption
Decrypt the ciphertext using the private key `(p, q)`.
```python
decrypted_message = decrypt(block_of_letters, ciphertext, p, q, k, l)
```
### Validation
Ensure the message contains only valid characters (spaces and lowercase English letters).
```python
is_valid = validator(message)
```

## Example
1. Input `k` and `l` for block sizes.
2. Generate keys.
3. Encrypt a message.
4. Decrypt the ciphertext back to the original message.

## Constraints
- Messages must contain only lowercase letters and spaces.
- The block size for ciphertext (`l`) must be greater than the block size for plaintext (`k`).

## Conclusion
This project demonstrates a robust implementation of the Rabin Cryptosystem. It showcases the use of mathematical principles to achieve secure message encryption and decryption.



# CRYSTALS-KYBER JavaScript

**CRYSTALS-KYBER** is a post-quantum key exchange protocol.

This protocol is used to securely establish symmetric keys between two parties. 

This JavaScript implementation is intended for client-side web browser applications but of course can be used for any JavaScript based application.

Most of this code was translated from [Nadim Kobeissi](https://nadim.computer)'s Go implementation of Kyber which can be found [here](https://github.com/symbolicsoft/kyber-k2so).

Code by the original designers (written in C) can be found [here](https://github.com/pq-crystals/kyber).

Kyber's original design comes in 512, 768, 1024 security strengths. This implementation only supports the security strength of 768 at the moment. In the future these strengths will be implemented as well as any updates if changes are made to the original design.

This code is the most up to date version based off the [NIST PQC Round 3 Submissions](https://csrc.nist.gov/projects/post-quantum-cryptography/round-3-submissions).

## Functionality

**KYBER-768** will securely distribute a 256 bit symmetric key between two parties. To safely transmit data over a channel using the key, AES-256 is recommended.

The exchange can be visualised below:

![](./diagram.jpeg)

## Usage
Using Node.js or React:
```bash
npm install sha3
```
Copy and paste kyber768.js file into the intended folder and export the KeyGen/Encrypt/Decrypt functions if needed.
```js
// To generate a public and private key pair (pk, sk)
var  pk_sk  =  KeyGen();
var  pk  =  pk_sk[0];
var  sk  =  pk_sk[1];

// To generate a random 256 bit symmetric key (ss) and its encapsulation (c)
var  c_ss  =  Encrypt(pk);
var  c  =  c_ss[0];
var  ss1  =  c_ss[1];

// To decapsulate and obtain the same symmetric key
var  ss2  =  Decrypt(c,sk);
```
To run code using Node.js:
```bash
node kyber768.js
```

## Disclaimer
All effort has been made to ensure this code is functional and operating as intended according to the original CRYSTALS-KYBER design. Any issues or concerns can be sent to amt597@uowmail.edu.au.

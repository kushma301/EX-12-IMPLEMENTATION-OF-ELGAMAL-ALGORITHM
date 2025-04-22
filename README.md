
## AIM:

To implement the ElGamal encryption and decryption algorithm using C for secure communication.


## ALGORITHM:
1.	Choose a large prime number p and a primitive root g of p.
2.	Select a private key x such that 1 < x < p.
3.	Compute the public key y = g^x mod p.
4.	To encrypt a message M:
a.	Choose a random integer k such that 1 < k < p.
b.	Compute C1 = g^k mod p.
c.	Compute C2 = (M * y^k) mod p.
d.	The ciphertext is the pair (C1, C2).
5.	To decrypt the ciphertext (C1, C2):
a.	Compute s = C1^(p-1-x) mod p.
b.	Compute the original message M = (C2 * s) mod p.
6.	Display the decrypted message.


## PROGRAM:

## OUTPUT:

## RESULT:

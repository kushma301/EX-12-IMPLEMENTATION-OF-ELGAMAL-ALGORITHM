
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
```
#include <stdio.h>
#include <math.h>


long long int modExp(long long int base, long long int exp, long long int mod) {
    long long int result = 1;
    while (exp > 0) {
        if (exp % 2 == 1) {
            result = (result * base) % mod;
        }
        base = (base * base) % mod;
        exp = exp / 2;
    }
    return result;
}

int main() 
    long long int p, g, privateKeyA, publicKeyA;
    long long int k, message, c1, c2, decryptedMessage;

    printf("Enter a large prime number (p): ");
    scanf("%lld", &p);
    printf("Enter a generator (g): ");
    scanf("%lld", &g);

    printf("Enter Alice's private key: ");
    scanf("%lld", &privateKeyA);

   
    publicKeyA = modExp(g, privateKeyA, p);
    printf("Alice's public key: %lld\n", publicKeyA);

    printf("Enter the message to encrypt (as a number): ");
    scanf("%lld", &message);
    printf("Enter a random number k: ");
    scanf("%lld", &k);

   
    c1 = modExp(g, k, p);
    c2 = (message * modExp(publicKeyA, k, p)) % p;
    printf("Encrypted message (c1, c2): (%lld, %lld)\n", c1, c2);

    decryptedMessage = (c2 * modExp(c1, p - 1 - privateKeyA, p)) % p;
    printf("Decrypted message: %lld\n", decryptedMessage);

    return 0;
}
```
## OUTPUT:
<img width="809" height="903" alt="Screenshot 2025-10-25 083053" src="https://github.com/user-attachments/assets/d01e104a-10a1-4118-9aa2-9f8a9c5c5486" />

## RESULT:
Hence  the ElGamal encryption and decryption algorithm using C for secure communication is executed successfully.

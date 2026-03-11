# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm
## NAME:LOESH M
## REG NO:212224040173
## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
```
#include <stdio.h>

 // Function to calculate (a^b) % P using modular exponentiation
 long long int power(long long int a, long long int b, long long int P)
 {
 long long int result = 1;
 a = a % P;

 while (b > 0)
 {
 if (b % 2 == 1) // If b is odd
 result = (result * a) % P;

 b = b >> 1; // b = b / 2
 a = (a * a) % P;
 }
 return result;
 }

 // Driver program
 int main()
 {
 long long int P, G, x, a, y, b, ka, kb;

 printf("\n***** Diffie-Hellman Key Exchange Algorithm *****\n\n");

 // Publicly known P and G
 printf("Enter the value of P (a prime number): ");
 scanf("%lld", &P);
 printf("The value of P: %lld\n", P);

 printf("Enter the value of G (a primitive root of P): ");
 scanf("%lld", &G);
 printf("The value of G: %lld\n\n", G);

 // Alice chooses private key a
 a = 4;
 printf("The private key a for Alice: %lld\n", a);
 x = power(G, a, P); // Alice's public key

 // Bob chooses private key b
 b = 3;
 printf("The private key b for Bob: %lld\n\n", b);
 y = power(G, b, P); // Bob's public key

 // Secret keys
 ka = power(y, a, P); // Alice computes
 kb = power(x, b, P); // Bob computes

 printf("Secret key for Alice: %lld\n", ka);
 printf("Secret key for Bob: %lld\n", kb);

 return 0;
 }


```


## Output:


<img width="837" height="640" alt="image" src="https://github.com/user-attachments/assets/d260136c-6f6c-436e-948b-77f1a312851f" />

## Result:
  The program is executed successfully


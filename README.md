## EX 10 : IMPLEMENTATION OF DIFFIE HELLMAN ALGORITHM

## AIM :
To implement key exchange between users using Diffie Hellman algorithm.

## ALGORITHM :
1.	Select a large prime number P and a primitive root G of P (publicly known).
2.	Alice selects a private key a and computes her public key x = (G^a) mod P.
3.	Bob selects a private key b and computes his public key y = (G^b) mod P.
4.	Alice and Bob exchange their public keys (x and y).
5.	Alice computes the secret key as ka = (y^a) mod P.
6.	Bob computes the secret key as kb = (x^b) mod P.
7.	Both ka and kb will be the same, forming a shared secret key for secure communication.


## PROGRAM :
```
#include <stdio.h>
#include <math.h>


long long int power(long long int a, long long int b, long long int P) {
    long long int result = 1;
    for (int i = 0; i < b; i++) {
        result = (result * a) % P;
    }
    return result;
}

int main() {
    long long int P, G, x, a, y, b, ka, kb;

    printf("\n***** Diffie-Hellman Key Exchange Algorithm *****\n");

    
    printf("\nEnter the value of P (prime number): ");
    scanf("%lld", &P);
    printf("Enter the value of G (primitive root of P): ");
    scanf("%lld", &G);

    a = 4; 
    b = 3; 

    printf("\nThe private key a for Alice: %lld", a);
    printf("\nThe private key b for Bob: %lld\n", b);

    x = power(G, a, P); 
    y = power(G, b, P); 

    printf("\nPublic key for Alice (x): %lld", x);
    printf("\nPublic key for Bob (y): %lld\n", y);


    ka = power(y, a, P); 
    kb = power(x, b, P); 
    printf("\nSecret key for Alice: %lld", ka);
    printf("\nSecret key for Bob: %lld\n", kb);

    if (ka == kb)
        printf("\n\nShared secret key established successfully!\n");
    else
        printf("\n\nError: Secret keys do not match!\n");

    return 0;
}
```
## OUTPUT:

<img width="581" height="463" alt="image" src="https://github.com/user-attachments/assets/2159dac1-9559-4033-9642-7a1ed357fc28" />

## RESULT :
The Diffie-Hellman key exchange algorithm has been successfully simulated, with correct execution	of	the	program	and	verification	of	the	results.

#### Name : Sowmya V
#### Reg no : 212222110045
#### Date : 

## EX - 8 : Implementation of Data Encryption Standard

### Aim:
To implementation of DES Encryption Standard

### Algorithm

1. Start.
2. Input the plaintext (maximum 64 characters).
3. Initialize the key as key = "DESKEY12".
4. Calculate the length of the plaintext.
5. Encrypt the plaintext
6. Display the encrypted text in hexadecimal format.
7. Decrypt the ciphertext
8. Display the decrypted text.
9. End.

### Program:
```
#include <stdio.h>
#include <string.h>
char key[8] = "DESKEY12";
void des_encrypt(char *plaintext, char *ciphertext) 
{
    int i;
    for (i = 0; i < strlen(plaintext); i++) 
    {
        ciphertext[i] = plaintext[i] ^ key[i % 8];  
    }
    ciphertext[i] = '\0'; 
}
void des_decrypt(char *ciphertext, char *plaintext) 
{
    int i;
    for (i = 0; i < strlen(ciphertext); i++) 
    {
        plaintext[i] = ciphertext[i] ^ key[i % 8];  
    }
    plaintext[i] = '\0';  
}
int main() 
{
    char plaintext[64];  
    char ciphertext[64]; 
    char decryptedtext[64]; 
    printf("Enter the plaintext (max 64 characters): ");
    fgets(plaintext, sizeof(plaintext), stdin);
    plaintext[strcspn(plaintext, "\n")] = '\0';  
    des_encrypt(plaintext, ciphertext);
    printf("Encrypted text: ");
    for (int i = 0; i < strlen(ciphertext); i++) 
    {
        printf("%02x", (unsigned char)ciphertext[i]);  
    }
    printf("\n");
    des_decrypt(ciphertext, decryptedtext);
    printf("Decrypted text: %s\n", decryptedtext);
    return 0;
}

```
### Output

![image](https://github.com/user-attachments/assets/0cc91a97-276a-45f3-a755-38a359c819df)

### Result
Implementation of Data Encryption Standard to encrypt and decrypt was successful.

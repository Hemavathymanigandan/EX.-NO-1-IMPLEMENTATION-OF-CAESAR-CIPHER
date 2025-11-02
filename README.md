# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```c
#include <stdio.h>
#include <ctype.h>  // for isalpha and isupper

void caesarCipher(char text[], int key) {
    for (int i = 0; text[i] != '\0'; i++) {
        char ch = text[i];
        if (isalpha(ch)) {  // check if it’s a letter
            char base = isupper(ch) ? 'A' : 'a';
            ch = (ch - base + key) % 26 + base; // shift
        }
        text[i] = ch;
    }
}

int main() {
    char text[100];
    int key;

    printf("Enter a message: ");
    fgets(text, sizeof(text), stdin);  // safe version of gets()

    printf("Enter key (1-25): ");
    scanf("%d", &key);

    caesarCipher(text, key);
    printf("Encrypted message: %s\n", text);

    // To decrypt, use 26 - key
    caesarCipher(text, 26 - key);
    printf("Decrypted message: %s\n", text);

    return 0;
}
```
## OUTPUT:
<img width="1916" height="722" alt="Screenshot 2025-11-02 134544" src="https://github.com/user-attachments/assets/08f4ae1d-072f-4062-b6d7-8b3c4ddf007a" />

## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.

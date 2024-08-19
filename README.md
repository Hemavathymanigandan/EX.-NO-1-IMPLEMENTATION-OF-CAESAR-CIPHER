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
#include <stdio.h>
#include <string.h>

void encrypt(char text[], int shift) 
{
    int i;
    char ch;
    
    for(i = 0; text[i] != '\0'; ++i) {
        ch = text[i];
        
        if(ch >= 'A' && ch <= 'Z') {
            ch = ch + shift;
            
            if(ch > 'Z') {
                ch = ch - 'Z' + 'A' - 1;
            }
            
            text[i] = ch;
        }
    
        else if(ch >= 'a' && ch <= 'z') {
            ch = ch + shift;
            
            if(ch > 'z') {
                ch = ch - 'z' + 'a' - 1;
            }
            
            text[i] = ch;
        }
    }
}

void decrypt(char text[], int shift) 
{
    int i;
    char ch;
    
    for(i = 0; text[i] != '\0'; ++i) {
        ch = text[i];
        
        if(ch >= 'A' && ch <= 'Z') {
            ch = ch - shift;
            
            if(ch < 'A') {
                ch = ch + 'Z' - 'A' + 1;
            }
            
            text[i] = ch;
        }
      
        else if(ch >= 'a' && ch <= 'z') {
            ch = ch - shift;
            
            if(ch < 'a') {
                ch = ch + 'z' - 'a' + 1;
            }
            
            text[i] = ch;
        }
    }
}

int main() 
{
    char text[100];
    int shift;
    
    printf("Enter a message to encrypt: ");
    gets(text);
    
    printf("Enter shift amount: ");
    scanf("%d", &shift);
 
    encrypt(text, shift);
    printf("Encrypted message: %s\n", text);
    
    decrypt(text, shift);
    printf("Decrypted message: %s\n", text);
    
    return 0;
}

## OUTPUT:
Enter a message to encrypt: goodmorning
Enter shift amount: 3
Encrypted message: jrrgpruqlqj
Decrypted message: goodmorning

## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.

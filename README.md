# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER
# Name: Santhosh A
# Reg no: 212225040378

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main()
{
char plain[100], cipher[100]; int key, i, length;
printf("Enter the plain text: ");
scanf("%s", plain);
printf("Enter the key value: ");
scanf("%d", &key);
printf("\nPLAIN TEXT: %s", plain);
printf("\nENCRYPTED TEXT: ");
length = strlen(plain);
for (i = 0; i < length; i++)
{
cipher[i] = plain[i] + key;
if (isupper(plain[i]) && cipher[i] > 'Z')
{
cipher[i]= cipher[i] - 26;
}
if (islower(plain[i]) && cipher[i] > 'z')
{
cipher[i] = cipher[i] - 26;
}
printf("%c", cipher[i]);
}
cipher[length] = '\0'; 
printf("\nDECRYPTED TEXT: ");
for (i = 0; i < length; i++)
{
plain[i] = cipher[i] - key;
if (isupper(cipher[i]) && plain[i] < 'A')
{
plain[i] = plain[i] + 26;
}
if (islower(cipher[i]) && plain[i] < 'a')
{
plain[i] = plain[i] + 26;
}
printf("%c", plain[i]);
}
plain[length] = '\0'; 
}
```


## OUTPUT:

<img width="1917" height="1136" alt="Screenshot 2026-10-21 143448" src="https://github.com/user-attachments/assets/2ab9e285-6b09-45e3-85c2-6e7623c53fdf" />

## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully

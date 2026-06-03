# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
#include <stdio.h>
#include <string.h>

int main()
{
    char msg[100];
    char rail[10][100];
    int rails, len;
    int row = 0, dir = 1;

    printf("Enter the message: ");
    scanf("%s", msg);

    printf("Enter number of rails: ");
    scanf("%d", &rails);

    len = strlen(msg);

    for(int i = 0; i < rails; i++)
    {
        for(int j = 0; j < len; j++)
        {
            rail[i][j] = '*';
        }
    }

    for(int i = 0; i < len; i++)
    {
        rail[row][i] = msg[i];

        row = row + dir;

        if(row == rails - 1 || row == 0)
        {
            dir = -dir;
        }
    }

    printf("\nENCRYPTED TEXT: ");

    for(int i = 0; i < rails; i++)
    {
        for(int j = 0; j < len; j++)
        {
            if(rail[i][j] != '*')
            {
                printf("%c", rail[i][j]);
            }
        }
    }

    return 0;
}
```
# OUTPUT
<img width="1919" height="975" alt="image" src="https://github.com/user-attachments/assets/b13c08b3-51e2-4dce-b1fe-9332e2a06819" />

# RESULT
Thus, the program is verified successfully

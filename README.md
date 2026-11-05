# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

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
    char text[100];
    char rail[20][100];
    int i, j, k;
    int row = 0, direction = 1;
    int rails, len;

    printf("Enter the plaintext: ");
    scanf("%s", text);

    printf("Enter the number of rails: ");
    scanf("%d", &rails);

    len = strlen(text);

    if (rails <= 1 || rails > len)
    {
        printf("Invalid number of rails\n");
        return 0;
    }

    for (i = 0; i < rails; i++)
    {
        for (j = 0; j < len; j++)
        {
            rail[i][j] = '\0';
        }
    }

    for (i = 0; i < len; i++)
    {
        rail[row][i] = text[i];

        if (row == 0)
            direction = 1;
        else if (row == rails - 1)
            direction = -1;

        row += direction;
    }

    printf("Ciphertext: ");

    for (i = 0; i < rails; i++)
    {
        for (j = 0; j < len; j++)
        {
            if (rail[i][j] != '\0')
                printf("%c", rail[i][j]);
        }
    }

    printf("\n");

    return 0;
}

```

# OUTPUT

<img width="807" height="637" alt="image" src="https://github.com/user-attachments/assets/160380e9-fc15-4c20-9101-f3e529951b77" />

# RESULT
Thus, the C program to implement the Rail Fence transposition technique was successfully executed, and the corresponding ciphertext was obtained.

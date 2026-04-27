# Ex. No : 1

# IMPLEMENTATION OF SYMBOL TABLE

# Register Number : 212224230304

# Date : 27.04.2026

# AIM:

To write a C program to implement a symbol table.

# ALGORITHM:

1. Start the program.
2. Get the input from the user with the terminating symbol ‘$’.
3. Allocate memory for the variable by dynamic memory allocation function.
4. If the next character of the symbol is an operator then only the memory is allocated.
5. While reading, the input symbol is inserted into symbol table along with its memory address.
6. The steps are repeated till ‘$’ is reached.
7. To reach a variable, enter the variable to be searched and symbol table has been checked for corresponding variable, the variable along with its address is displayed as result.
8. Stop the program.

# PROGRAM:

~~~
#include <stdio.h>
#include <ctype.h>
#include <string.h>
#include <stdlib.h>

#define MAX_EXPRESSION_SIZE 100

int main() {
    int i = 0, j = 0, x = 0, n, flag = 0, k;
    char b[MAX_EXPRESSION_SIZE], d[15], c, srch;

    printf("Enter the Expression terminated by $: ");

    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }

    b[i] = '\0';
    n = i - 1;

    printf("\nGiven Expression: %s\n", b);

    printf("\nSymbol Table\n");
    printf("Symbol\tType\t\tAddress\n");

    for (j = 0; j <= n; j++) {
        c = b[j];

        if (isalpha((unsigned char)c)) {
            int alreadyExists = 0;

            for (k = 0; k < x; k++) {
                if (d[k] == c) {
                    alreadyExists = 1;
                    break;
                }
            }

            if (!alreadyExists) {
                d[x] = c;
                printf("%c\tidentifier\t%p\n", c, (void*)&d[x]);
                x++;
            }
        }
    }

    // Clear input buffer
    while ((c = getchar()) != '\n' && c != EOF);

    printf("\nEnter the symbol to search: ");
    srch = getchar();

    for (i = 0; i < x; i++) {
        if (srch == d[i]) {
            printf("Symbol %c Found @ address %p\n", srch, (void*)&d[i]);
            flag = 1;
            break;
        }
    }

    if (flag == 0)
        printf("Symbol Not Found\n");

    return 0;
}

~~~
# OUTPUT:

<img width="555" height="419" alt="17773124000805057144460708329158" src="https://github.com/user-attachments/assets/fd4cb76c-3ee8-4a4f-82d3-76e3dc52f000" />



<img width="521" height="462" alt="17773124190162960338428997690925" src="https://github.com/user-attachments/assets/d39f552c-1f23-40a3-8d02-0196ad7e2222" />

# RESULT:

The program to implement a symbol table is executed and the output is verified.

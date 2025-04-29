EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:


#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void swap(char *x, char *y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}


int cmpfunc(const void *a, const void *b) {
    return (*(char *)a - *(char *)b);
}


void reverse(char *s, int i, int j) {
    while (i < j) {
        swap(&s[i], &s[j]);
        i++;
        j--;
    }
}

int next_permutation(char *s, int len) {
    int i = len - 2;
    while (i >= 0 && s[i] >= s[i + 1])
        i--;
    if (i < 0)
        return 0;

    int j = len - 1;
    while (s[j] <= s[i])
        j--;

    swap(&s[i], &s[j]);
    reverse(s, i + 1, len - 1);
    return 1;
}

int main() {
    char *s;
    int len;

    // Step 3: Memory allocation
    s = (char *)malloc(100 * sizeof(char));
    if (s == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    printf("Enter a string: ");
    scanf("%s", s);

    len = strlen(s);

    qsort(s, len, sizeof(char), cmpfunc);

    printf("%s\n", s);

    while (next_permutation(s, len)) {
        printf("%s\n", s);
    }

    free(s);

    return 0;
}





Output:



![image](https://github.com/user-attachments/assets/17d188fd-1813-4797-8b53-1ed89203e9ed)







Result:
Thus, the program is verified successfully

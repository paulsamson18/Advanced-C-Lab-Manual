
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

#include <stdio.h>
#include <string.h>

int main() {
    char a[50];
    int i, h, c;

    printf("Enter a string containing digits: ");
    scanf("%s", a);

    for (h = 0; h < 10; h++) {
        c = 0; 
        for (i = 0; i < strlen(a); i++) {
            if (a[i] == (h + '0')) {
                c++;
            }
        }
        printf("%d ", c);
    }

    printf("\n");
    return 0;
}






Output:



![image](https://github.com/user-attachments/assets/89444f99-39cd-47b5-bb80-5b059047e0d3)





Result:
Thus, the program is verified successfully

# EXP NO: 6 - C PROGRAM TO PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER

## Aim
To write a C program to print the lowercase English word corresponding to a number.

## Algorithm
1. Start.
2. Declare an integer variable n and read its value.
3. Use a switch statement on n:
   - Case 1: print "one"
   - Case 2: print "two"
   - ...
   - Case 9: print "nine"
   - Default: print "Greater than 9"
4. Stop.

## Program
```c
#include <stdio.h>
int main() {
    int n;
    scanf("%d", &n);
    switch (n) {
        case 1: printf("one"); break;
        case 2: printf("two"); break;
        case 3: printf("three"); break;
        case 4: printf("four"); break;
        case 5: printf("five"); break;
        case 6: printf("six"); break;
        case 7: printf("seven"); break;
        case 8: printf("eight"); break;
        case 9: printf("nine"); break;
        default: printf("Greater than 9");
    }
}
```

## Output

<img width="1917" height="552" alt="image" src="https://github.com/user-attachments/assets/cad6ccb5-d2e7-4c54-99a8-cb0e924aa750" />


## Result
Thus, the program is verified successfully.

---

# EXP NO: 7 - C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS IN A SINGLE LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 9

## Aim
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 9.

## Algorithm
1. Start.
2. Declare a char array a[50] and read the string.
3. Run an outer loop for each digit from '0' to '9'.
4. Initialize counter c to 0.
5. For each character in the string, increment c if it matches the current digit.
6. Print c followed by a space, then move to the next digit.
7. Stop.

## Program
```c
#include <stdio.h>
int main() {
    char a[50];
    scanf("%s", a);
    for (char d = '0'; d <= '9'; d++) {
        int c = 0;
        for (int i = 0; a[i]; i++)
            if (a[i] == d) c++;
        printf("%d ", c);
    }
}
```

## Output

<img width="1917" height="386" alt="image" src="https://github.com/user-attachments/assets/324e4f55-8ca2-4e4c-abdf-f3f3e6d6f8a7" />



## Result
Thus, the program is verified successfully.

---

# EXP NO: 8 - C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER

## Aim
To write a C program to print all permutations of a set of strings in strict lexicographical order.

## Algorithm
1. Start.
2. Declare s (pointer to an array of strings) and n (number of strings).
3. Memory allocation: dynamically allocate memory for s.
4. Input: read n, then allocate memory for and read each string in s.
5. Sort the strings in ascending order.
6. Permutation generation loop: print the current arrangement, then generate the next lexicographic permutation; repeat until none remains.
7. Memory deallocation: free each string in s, then free s.
8. Stop.

## Program
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int cmp(const void *a, const void *b) { return strcmp(*(char **)a, *(char **)b); }

int next(char **s, int n) {
    int i = n - 2, j = n - 1;
    while (i >= 0 && strcmp(s[i], s[i + 1]) >= 0) i--;
    if (i < 0) return 0;
    while (strcmp(s[i], s[j]) >= 0) j--;
    char *t = s[i]; s[i] = s[j]; s[j] = t;
    for (int a = i + 1, b = n - 1; a < b; a++, b--) { t = s[a]; s[a] = s[b]; s[b] = t; }
    return 1;
}

int main() {
    int n;
    scanf("%d", &n);
    char **s = malloc(n * sizeof(char *));
    for (int i = 0; i < n; i++) {
        s[i] = malloc(20);
        scanf("%s", s[i]);
    }
    qsort(s, n, sizeof(char *), cmp);
    do {
        for (int i = 0; i < n; i++) printf("%s%c", s[i], i == n - 1 ? '\n' : ' ');
    } while (next(s, n));
    for (int i = 0; i < n; i++) free(s[i]);
    free(s);
}
```

## Output

<img width="1912" height="527" alt="image" src="https://github.com/user-attachments/assets/72520a83-b41b-498a-900a-a4d9ca0240e5" />



## Result
Thus, the program is verified successfully.

---

# EXP NO: 9 - C PROGRAM TO PRINT A PATTERN OF NUMBERS FROM 1 TO N

## Aim
To write a C program to print a square pattern of numbers from 1 to n, with n on the outer border and 1 at the center.

## Algorithm
1. Start.
2. Declare integer variables n, i, j, min.
3. Read the value of n.
4. Calculate the side length of the square matrix: len = 2 * n - 1.
5. Matrix generation loop: for each i and j from 0 to len - 1:
   - Calculate min as the minimum distance to the four borders.
   - Print n - min.
6. Print a new line after each row.
7. Stop.

## Program
```c
#include <stdio.h>
int main() {
    int n, len, min;
    scanf("%d", &n);
    len = 2 * n - 1;
    for (int i = 0; i < len; i++) {
        for (int j = 0; j < len; j++) {
            min = i;
            if (j < min) min = j;
            if (len - 1 - i < min) min = len - 1 - i;
            if (len - 1 - j < min) min = len - 1 - j;
            printf("%d ", n - min);
        }
        printf("\n");
    }
}
```

## Output

<img width="1917" height="515" alt="image" src="https://github.com/user-attachments/assets/2ce60aab-9960-4b35-b8ac-0ebe2324efa7" />


## Result
Thus, the program is verified successfully.

---

# EXP NO: 10 - C PROGRAM TO FIND THE SQUARE OF A NUMBER USING A FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

## Aim
To write a C program that calculates the square of a number using a function that takes no arguments but returns the square of the number.

## Algorithm
1. Start.
2. Define a function square() with no parameters that returns an integer.
3. Inside the function:
   - Declare an integer variable to store the number.
   - Ask the user to input a number.
   - Calculate the square by multiplying the number by itself.
   - Return the squared value.
4. In the main function, call square() and display the result.
5. Stop.

## Program
```c
#include <stdio.h>
int square() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    return n * n;
}
int main() {
    printf("Square = %d", square());
}
```

## Output

<img width="1911" height="357" alt="image" src="https://github.com/user-attachments/assets/cce59eaa-8280-46b6-8cf5-8dd22d423179" />


## Result
Thus, the program is verified successfully.

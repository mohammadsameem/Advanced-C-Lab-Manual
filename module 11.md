# EXP NO: 21 - C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER

## Aim
To write a C program to create a function to find the greatest number.

## Algorithm
1. Include the necessary header #include <stdio.h>.
2. Define the function max_of_four that uses a series of if and else if statements to compare the values and return the maximum among them.
3. Declare variables n1, n2, n3, n4 and greater to store the user input and the result.
4. Use scanf to take four integers as input.
5. Call the max_of_four function with the input integers and store the result in the greater variable.
6. Print the value of greater.
7. Stop.

## Program
```c
#include <stdio.h>

int max_of_four(int a, int b, int c, int d) {
    if (a >= b && a >= c && a >= d)
        return a;
    else if (b >= c && b >= d)
        return b;
    else if (c >= d)
        return c;
    else
        return d;
}

int main() {
    int n1, n2, n3, n4, greater;
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);
    greater = max_of_four(n1, n2, n3, n4);
    printf("%d", greater);
}
```

## Output
<img width="1917" height="737" alt="image" src="https://github.com/user-attachments/assets/70e7acbf-0574-4771-b4c5-ecf649bd24c0" />


## Result
Thus, the program that creates a function to find the greatest number is verified successfully.

---

# EXP NO: 22 - C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND XOR COMPARISONS

## Aim
To write a C program to print the maximum values of the AND, OR and XOR operations (each less than k) over all pairs of integers from 1 to n.

## Algorithm
1. Define a function calculate_the_max that takes two integers n and k as parameters.
2. Declare variables a, o and x to store the maximum values for the AND, OR and XOR operations, and initialize them to 0.
3. Use nested loops to iterate through pairs of integers (i, j) with 1 <= i < j <= n.
4. Within the loops, check if i&j, i|j and i^j are less than k and greater than the current maximum, and update a, o and x.
5. Declare variables n and k to store the user input.
6. Use scanf to take the two integers as input.
7. Call the calculate_the_max function with the input values and print a, o and x on separate lines.
8. Stop.

## Program
```c
#include <stdio.h>

void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            if ((i & j) < k && (i & j) > a) a = i & j;
            if ((i | j) < k && (i | j) > o) o = i | j;
            if ((i ^ j) < k && (i ^ j) > x) x = i ^ j;
        }
    }
    printf("%d\n%d\n%d\n", a, o, x);
}

int main() {
    int n, k;
    scanf("%d %d", &n, &k);
    calculate_the_max(n, k);
}
```

## Output
<img width="1917" height="600" alt="image" src="https://github.com/user-attachments/assets/dc49fc5e-9ecf-4387-9581-bb2df36a59e5" />


## Result
Thus, the program to print the maximum values for the AND, OR and XOR comparisons is verified successfully.

---

# EXP NO: 23 - C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS

## Aim
To write a C program to implement the logic for requests on shelves of books (add a book, find a book's page count, find the number of books on a shelf).

## Algorithm
1. Declare variables noshel and noque to store the number of shelves and the number of queries.
2. Use scanf to take the two integers as input.
3. Declare a 2D array shelarr to represent the shelves and books, and an array nobookarr to store the number of books on each shelf.
4. Declare variables k and c to store the query type and the total number of books.
5. Use a for loop to iterate over the queries:
   - Type 1: add a book with y pages to shelf x and increment c.
   - Type 2: print the number of pages of the y-th book on shelf x.
   - Type 3: print the number of books on shelf x.
6. Stop.

## Program
```c
#include <stdio.h>

int shelarr[100][100], nobookarr[100];

int main() {
    int noshel, noque, k, c = 0, x, y;
    scanf("%d %d", &noshel, &noque);
    for (int i = 0; i < noque; i++) {
        scanf("%d", &k);
        if (k == 1) {
            scanf("%d %d", &x, &y);
            shelarr[x][nobookarr[x]++] = y;
            c++;
        } else if (k == 2) {
            scanf("%d %d", &x, &y);
            printf("%d\n", shelarr[x][y]);
        } else {
            scanf("%d", &x);
            printf("%d\n", nobookarr[x]);
        }
    }
}
```

## Output
<img width="1901" height="632" alt="image" src="https://github.com/user-attachments/assets/af5d944e-a672-4179-a878-6aaf635e30a3" />


## Result
Thus, the program to write the logic for the requests is verified successfully.

---

# EXP NO: 24 - C PROGRAM TO PRINT THE SUM OF THE INTEGERS IN THE ARRAY

## Aim
To write a C program to print the sum of the integers in an array.

## Algorithm
1. Declare a variable n to store the number of integers.
2. Use scanf to take the integer n as input.
3. Declare an array a of size n to store the integers.
4. Declare a variable sum and initialize it to zero.
5. Use a for loop to iterate n times:
   - Use scanf to input each integer and add it to sum.
6. Print the final sum using printf.
7. Stop.

## Program
```c
#include <stdio.h>

int main() {
    int n, sum = 0;
    scanf("%d", &n);
    int a[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }
    printf("%d", sum);
}
```

## Output
<img width="1912" height="441" alt="image" src="https://github.com/user-attachments/assets/113d1757-12b9-4c30-9d4c-69c2c620178e" />


## Result
Thus, the program that prints the sum of the integers in the array is verified successfully.

---

# EXP NO: 25 - C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE

## Aim
To write a C program that counts the number of words in a given sentence.

## Algorithm
1. Input the sentence from the user.
2. Initialize a counter variable count to 0 and a flag variable to 0.
3. Process each character of the sentence:
   - If the character is not a space, and it is the first non-space character after a space or at the start, increment the word count.
   - If the character is a space, reset the flag.
4. Skip over the spaces and treat each word as a sequence of characters separated by spaces.
5. Display the total word count.
6. Stop.

## Program
```c
#include <stdio.h>

int main() {
    char s[100];
    int count = 0, inWord = 0;
    fgets(s, 100, stdin);
    for (int i = 0; s[i]; i++) {
        if (s[i] != ' ' && s[i] != '\n') {
            if (!inWord) {
                count++;
                inWord = 1;
            }
        } else
            inWord = 0;
    }
    printf("Number of words = %d", count);
}
```

## Output
<img width="1917" height="555" alt="image" src="https://github.com/user-attachments/assets/3083ac44-bd11-4027-83d0-a41382781eec" />


## Result
Thus, the program that counts the number of words in a given sentence is verified successfully.

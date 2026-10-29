EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:
~~~
#include <stdio.h>
struct numbers {
    int a, b;
};
struct numbers add(struct numbers n) {
    n.a = n.a + n.b;
    return n;
}
int main() {
    struct numbers n, r;\
    scanf("%d%d", &n.a, &n.b);
    r = add(n);
    printf("Sum = %d", r.a);
}
~~~

Output:

<img width="1855" height="530" alt="image" src="https://github.com/user-attachments/assets/e94f0e9a-090b-481a-baa2-e6aa26f93ef4" />

<img width="471" height="258" alt="image" src="https://github.com/user-attachments/assets/e4b163fb-ee79-42c1-8a15-f6bf7fce3979" />





Result:
Thus, the program is verified successfully

# EXP NO: 11 - C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY

## Aim
To write a C program to display stack elements using an array.

## Algorithm
1. Include the necessary header files.
2. Declare the global variables: the stack array and top.
3. Define the display function.
4. In main, initialize the stack and set top to -1.
5. Perform stack operations (push, pop, etc.).
6. Use the display function to show the contents of the stack.
7. Stop.

## Program
```c
#include <stdio.h>
#define MAX 5

int stack[MAX], top = -1;

void display() {
    if (top == -1) {
        printf("Stack is empty\n");
        return;
    }
    printf("Stack elements:\n");
    for (int i = top; i >= 0; i--)
        printf("%d\n", stack[i]);
}

int main() {
    stack[++top] = 10;
    stack[++top] = 20;
    stack[++top] = 30;
    display();
}
```

## Output

<img width="1917" height="595" alt="image" src="https://github.com/user-attachments/assets/de36ab0e-8622-47e0-80b5-fcc3caf4017e" />


## Result
Thus, the program to display stack elements using an array is verified successfully.

---

# EXP NO: 12 - PROGRAM TO PUSH THE GIVEN ELEMENT INTO A STACK USING ARRAY

## Aim
To create a C program to push the given element into a stack using an array.

## Algorithm
1. Declare global variables for the stack size, top index and the stack itself.
2. Define the push function to add a floating-point number to the stack.
3. Initialize the stack size, top index and the stack.
4. Call the push function as needed.
5. Stop.

## Program
```c
#include <stdio.h>
#define MAX 5

float stack[MAX];
int top = -1;

void push(float x) {
    if (top == MAX - 1) {
        printf("Stack overflow\n");
        return;
    }
    stack[++top] = x;
    printf("%.2f pushed\n", x);
}

int main() {
    push(1.5);
    push(2.5);
    push(3.5);
    printf("Top element = %.2f\n", stack[top]);
}
```

## Output

<img width="1913" height="498" alt="image" src="https://github.com/user-attachments/assets/ca8bf829-6a82-41cc-9c6f-537881d38e55" />


## Result
Thus, the program to push the given element into a stack using array is verified successfully.

---

# EXP NO: 13 - C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY

## Aim
To write a C program to display queue elements using an array.

## Algorithm
1. Declare global variables for the queue, rear, front and the loop counter.
2. Define the display function to print the elements of the queue.
3. Initialize the queue, rear and front.
4. Call the display function and perform other queue operations as needed.
5. Stop.

## Program
```c
#include <stdio.h>
#define MAX 5

int queue[MAX] = {10, 20, 30};
int front = 0, rear = 2;

void display() {
    if (front == -1) {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements: ");
    for (int i = front; i <= rear; i++)
        printf("%d ", queue[i]);
    printf("\n");
}

int main() {
    display();
}
```

## Output
<img width="1915" height="626" alt="image" src="https://github.com/user-attachments/assets/d3969eaf-2e98-4e6f-9bd0-e2b786288be4" />


## Result
Thus, the program to display queue elements using array is verified successfully.

---

# EXP NO: 14 - C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY

## Aim
To write a C program to insert elements in a queue using an array.

## Algorithm
1. Declare global variables for the size, rear, front and the queue itself.
2. Define the enqueue function to add a float to the queue.
3. Initialize rear and front to -1 and set the size of the queue.
4. Call the enqueue function as needed.
5. Stop.

## Program
```c
#include <stdio.h>
#define MAX 5

float queue[MAX];
int front = -1, rear = -1;

void enqueue(float x) {
    if (rear == MAX - 1) {
        printf("Queue overflow\n");
        return;
    }
    if (front == -1) front = 0;
    queue[++rear] = x;
    printf("%.2f inserted\n", x);
}

int main() {
    enqueue(1.5);
    enqueue(2.5);
    enqueue(3.5);
}
```

## Output

<img width="1912" height="572" alt="image" src="https://github.com/user-attachments/assets/807c6013-f7b5-41dd-be98-b0e0fa46b3fd" />


## Result
Thus, the program to insert elements in queue using array is verified successfully.

---

# EXP NO: 15 - C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

## Aim
To create a function in C that deletes an element from a queue implemented using an array.

## Algorithm
1. Check if the queue is empty:
   - If front is -1, print that the queue is empty and return.
2. Delete the front element:
   - Print the element at the front index.
   - Increment front by 1.
3. Check if the queue becomes empty after deletion:
   - If front > rear, reset both front and rear to -1.
4. End the function.

## Program
```c
#include <stdio.h>
#define MAX 5

int queue[MAX] = {10, 20, 30};
int front = 0, rear = 2;

void dequeue() {
    if (front == -1) {
        printf("Queue is empty\n");
        return;
    }
    printf("Deleted: %d\n", queue[front]);
    front++;
    if (front > rear)
        front = rear = -1;
}

int main() {
    dequeue();
    dequeue();
    dequeue();
    dequeue();
}
```

## Output

<img width="1917" height="497" alt="image" src="https://github.com/user-attachments/assets/f6eab476-fbe4-44d6-bcb6-8c85650289de" />

## Result
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.

# EXP NO: 26 - C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST

## Aim
To write a C program to display stack elements using a linked list.

## Algorithm
1. Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2. Declare a global variable head representing the starting node of the linked list.
3. Define a function display to print the elements of the linked list.
4. Declare a pointer p and initialize it with head.
5. Use a while loop to traverse the linked list until p is NULL:
   - Print the data of the current node.
   - Move to the next node using the next pointer.
6. Stop.

## Program
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};
struct Node *head = NULL;

void push(int x) {
    struct Node *p = malloc(sizeof(struct Node));
    p->data = x;
    p->next = head;
    head = p;
}

void display() {
    struct Node *p = head;
    if (p == NULL) {
        printf("Stack is empty\n");
        return;
    }
    printf("Stack elements:\n");
    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main() {
    push(10);
    push(20);
    push(30);
    display();
}
```

## Output
<img width="1906" height="640" alt="image" src="https://github.com/user-attachments/assets/928be18a-7fa9-44f7-86a8-e4697ad6d1f0" />


## Result
Thus, the program to display stack elements using linked list is verified successfully.

---

# EXP NO: 27 - C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST

## Aim
To write a C program to pop an element from the given stack using a linked list.

## Algorithm
1. Check for an empty stack:
   - If head is equal to NULL, print "Stack is empty."
   - Else proceed to the next step.
2. Store the top node in a temporary pointer and print its data.
3. Set head to point to the next node in the stack.
4. Free the memory of the popped node.
5. Stop.

## Program
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};
struct Node *head = NULL;

void push(int x) {
    struct Node *p = malloc(sizeof(struct Node));
    p->data = x;
    p->next = head;
    head = p;
}

void pop() {
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    struct Node *temp = head;
    printf("Popped: %d\n", temp->data);
    head = head->next;
    free(temp);
}

int main() {
    push(10);
    push(20);
    pop();
    pop();
    pop();
}
```

## Output
<img width="1916" height="643" alt="image" src="https://github.com/user-attachments/assets/6cd970cc-981c-40c9-8127-26016f112736" />


## Result
Thus, the program to pop an element from the given stack using linked list is verified successfully.

---

# EXP NO: 28 - C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST

## Aim
To write a C program to display queue elements using a linked list.

## Algorithm
1. Check if the queue is empty (front is NULL) and print a message if it is.
2. Display the queue elements:
   - Start from the node pointed to by front.
   - Print the data of the current node.
   - Update the pointer to the next node.
3. Repeat until the pointer becomes NULL.
4. End the display function.

## Program
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};
struct Node *front = NULL, *rear = NULL;

void enqueue(int x) {
    struct Node *p = malloc(sizeof(struct Node));
    p->data = x;
    p->next = NULL;
    if (front == NULL)
        front = rear = p;
    else {
        rear->next = p;
        rear = p;
    }
}

void display() {
    struct Node *p = front;
    if (p == NULL) {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements: ");
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }
    printf("\n");
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
}
```

## Output
<img width="1897" height="631" alt="image" src="https://github.com/user-attachments/assets/6442542c-4ae6-43f0-af16-a5ad7f1b3ed7" />


## Result
Thus, the program to display queue elements using linked list is verified successfully.

---

# EXP NO: 29 - C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

## Aim
To write a C program to insert elements in a queue using a linked list.

## Algorithm
1. Allocate memory for a new node p.
2. Set the data of p and set its next pointer to NULL.
3. Check if the queue is empty:
   - If it is, set both front and rear to point to the new node p.
   - Otherwise, set the next pointer of the current rear to point to p and update rear to p.
4. End of the enqueue operation.

## Program
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};
struct Node *front = NULL, *rear = NULL;

void enqueue(int x) {
    struct Node *p = malloc(sizeof(struct Node));
    p->data = x;
    p->next = NULL;
    if (front == NULL)
        front = rear = p;
    else {
        rear->next = p;
        rear = p;
    }
    printf("%d inserted\n", x);
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
}
```

## Output
<img width="1907" height="630" alt="image" src="https://github.com/user-attachments/assets/a6080fd2-6575-47b0-a3f6-3a1c8c5892ed" />


## Result
Thus, the program to insert elements in queue using linked list is verified successfully.

---

# EXP NO: 30 - C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST

## Aim
To write a C function to retrieve the "peek" (the front element) of a queue implemented using a linked list.

## Algorithm
1. Check if the queue is empty:
   - If the front pointer is NULL, print a message that the queue is empty and return an error value (-1).
2. Access the front element:
   - If the queue is not empty, return the data stored in the front node of the linked list.
3. Stop.

## Program
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};
struct Node *front = NULL, *rear = NULL;

void enqueue(int x) {
    struct Node *p = malloc(sizeof(struct Node));
    p->data = x;
    p->next = NULL;
    if (front == NULL)
        front = rear = p;
    else {
        rear->next = p;
        rear = p;
    }
}

int peek() {
    if (front == NULL) {
        printf("Queue is empty\n");
        return -1;
    }
    return front->data;
}

int main() {
    enqueue(10);
    enqueue(20);
    printf("Front element = %d", peek());
}
```

## Output
<img width="1911" height="643" alt="image" src="https://github.com/user-attachments/assets/8b6f558f-10d4-403b-90ed-6f83b1ee1cf9" />

## Result
Thus, the function to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.

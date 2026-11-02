# EXP NO: 16 - C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST

## Aim
To write a C program to search a given element in the given linked list.

## Algorithm
1. Define the structure for a node in a linked list.
2. Define the search function to find a specific character in the linked list.
3. Initialize the head of the linked list.
4. Call the search function and print whether the element is found.
5. Stop.

## Program
```c
#include <stdio.h>

struct Node {
    char data;
    struct Node *next;
};

void search(struct Node *head, char key) {
    int pos = 1;
    while (head != NULL) {
        if (head->data == key) {
            printf("%c found at position %d\n", key, pos);
            return;
        }
        head = head->next;
        pos++;
    }
    printf("%c not found\n", key);
}

int main() {
    struct Node c = {'c', NULL};
    struct Node b = {'b', &c};
    struct Node a = {'a', &b};
    search(&a, 'b');
    search(&a, 'z');
}
```

## Output

<img width="1910" height="472" alt="image" src="https://github.com/user-attachments/assets/9e68b1ff-13f1-46e5-9246-64eede830427" />


## Result
Thus, the program to search a given element in the given linked list is verified successfully.

---

# EXP NO: 17 - PROGRAM TO INSERT A NODE IN A LINKED LIST

## Aim
To write a C program to insert a node in a linked list.

## Algorithm
1. Define the structure for a node in a linked list.
2. Define the insert function to insert a new node with character data at the end of the linked list.
3. Initialize the head of the linked list to NULL.
4. Call the insert function and display the list.
5. Stop.

## Program
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *next;
};

void insert(struct Node **head, char ch) {
    struct Node *n = malloc(sizeof(struct Node));
    n->data = ch;
    n->next = NULL;
    if (*head == NULL) {
        *head = n;
        return;
    }
    struct Node *t = *head;
    while (t->next != NULL)
        t = t->next;
    t->next = n;
}

void display(struct Node *t) {
    while (t != NULL) {
        printf("%c -> ", t->data);
        t = t->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = NULL;
    insert(&head, 'a');
    insert(&head, 'b');
    insert(&head, 'c');
    display(head);
}
```

## Output
<img width="1917" height="632" alt="image" src="https://github.com/user-attachments/assets/c557b1ae-c83f-4889-86d2-30d121582176" />


## Result
Thus, the program to insert a node in a linked list is verified successfully.

---

# EXP NO: 18 - C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST

## Aim
To write a C program to traverse a doubly linked list.

## Algorithm
1. Initialize a temporary pointer (temp) to the head of the list.
2. Use a while loop to traverse the list until the end (temp == NULL) is reached.
3. Inside the loop, print the data of the current node.
4. Move to the next node by updating temp (temp = temp->next).
5. Stop.

## Program
```c
c
```

## Output
<img width="1917" height="641" alt="image" src="https://github.com/user-attachments/assets/ad178b9d-e691-4d0b-bb24-7e89961ba3a3" />


## Result
Thus, the program to traverse a doubly linked list is verified successfully.

---

# EXP NO: 19 - C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST

## Aim
To write a C program to insert an element in a doubly linked list.

## Algorithm
1. Create a new node (newNode) and allocate memory for it.
2. Set the data of the new node to the provided value.
3. If the list is empty, set the new node as the head.
4. If the list is not empty, traverse the list to find the last node.
5. Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
6. Stop.

## Program
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *prev, *next;
};

void insert(struct Node **head, int val) {
    struct Node *newNode = malloc(sizeof(struct Node));
    newNode->data = val;
    newNode->prev = newNode->next = NULL;
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    struct Node *t = *head;
    while (t->next != NULL)
        t = t->next;
    t->next = newNode;
    newNode->prev = t;
}

int main() {
    struct Node *head = NULL;
    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    for (struct Node *t = head; t != NULL; t = t->next)
        printf("%d ", t->data);
}
```

## Output
<img width="1917" height="631" alt="image" src="https://github.com/user-attachments/assets/699bdd01-4b68-43af-97b5-f1885feb4701" />


## Result
Thus, the program to insert an element in doubly linked list is verified successfully.

---

# EXP NO: 20 - C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

## Aim
To write a C function that deletes a given element from a linked list.

## Algorithm
1. Check if the linked list is empty:
   - If head is NULL, print that the list is empty and exit the function.
2. Traverse the linked list from the head to find the node that contains the given element.
3. Handle deletion of the first node:
   - If the element is in the head node, set head = head->next.
   - Free the memory of the deleted node and exit the function.
4. Delete from the middle or end:
   - Keep track of the previous node while traversing.
   - When the node is found, set prev->next = current->next.
   - Free the memory of the deleted node.
5. If the element is not found in any node, print that the element is not present in the list.
6. End the function.

## Program
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

void insert(struct Node **head, int val) {
    struct Node *n = malloc(sizeof(struct Node));
    n->data = val;
    n->next = NULL;
    if (*head == NULL) {
        *head = n;
        return;
    }
    struct Node *t = *head;
    while (t->next != NULL)
        t = t->next;
    t->next = n;
}

void deleteNode(struct Node **head, int key) {
    if (*head == NULL) {
        printf("List is empty\n");
        return;
    }
    struct Node *cur = *head, *prev = NULL;
    if (cur->data == key) {
        *head = cur->next;
        free(cur);
        printf("%d deleted\n", key);
        return;
    }
    while (cur != NULL && cur->data != key) {
        prev = cur;
        cur = cur->next;
    }
    if (cur == NULL) {
        printf("%d not found\n", key);
        return;
    }
    prev->next = cur->next;
    free(cur);
    printf("%d deleted\n", key);
}

void display(struct Node *t) {
    printf("List: ");
    while (t != NULL) {
        printf("%d -> ", t->data);
        t = t->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = NULL;
    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    deleteNode(&head, 20);
    display(head);
    deleteNode(&head, 40);
    deleteNode(&head, 10);
    display(head);
}
```

## Output
<img width="1917" height="642" alt="image" src="https://github.com/user-attachments/assets/1a38ad70-cf71-43fd-ae65-d7292da08247" />


## Result
Thus, the function that deletes a given element from a linked list is verified successfully.

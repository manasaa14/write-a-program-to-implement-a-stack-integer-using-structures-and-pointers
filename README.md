# write-a-program-to-implement-a-stack-integer-using-structures-and-pointers
implement a stack using structures and pointers
#include <stdio.h>
#include <stdlib.h>
#define SIZE 5

typedef struct {
    int top;
    int *items;
} Stack;

void init(Stack *s) {
    s->top = -1;
    s->items = (int *)malloc(SIZE * sizeof(int));
}

void push(Stack *s, int value) {
    if (s->top == SIZE - 1) {
        printf("Stack Overflow\n");
        return;
    }
    s->items[++(s->top)] = value;
    printf("Pushed %d\n", value);
}

// Pop an element from the stack
int pop(Stack *s) {
    if (s->top == -1) {
        printf("Stack Underflow\n");
        return -1;
    }
    return s->items[(s->top)--];
}

int peek(Stack *s) {
    if (s->top == -1) {
        printf("Stack is empty\n");
        return -1;
    }
    return s->items[s->top];
}

// Display all elements
void display(Stack *s) {
    if (s->top == -1) {
        printf("Stack is empty\n");
        return;
    }
    printf("Stack elements: ");
    for (int i = 0; i <= s->top; i++) {
        printf("%d ", s->items[i]);
    }
    printf("\n");
}

// Main function to test the stack
int main() {
    Stack s;
    init(&s);

    push(&s, 10);
    push(&s, 20);
    push(&s, 30);
    display(&s);

    printf("Top element: %d\n", peek(&s));
    printf("Popped element: %d\n", pop(&s));
    display(&s);

  
    return 0;
    }

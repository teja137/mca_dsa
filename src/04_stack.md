stack is a linear data structure.

It follows LIFO (Last In, First Out) principle. The last element inserted into the stack is the first one to be removed.

The last element inserted into the stack is the first one to be removed.

pseudo code for array implementation:


Initialize stack[MAX_SIZE] and top = -1

void PUSH(element) {
    If top == MAX_SIZE - 1 {
        Print "Stack Overflow"
        Return
    }
    Increment top by 1
    stack[top] = element
}

void POP() {
    If top == -1 {
        Print "Stack Underflow"
        Return
    }
    Print "Popped element:", stack[top]
    Decrement top by 1
}

void PEEK() {
    If top == -1 {
        Print "Stack is empty"
        Return
    }
    Print "Top element:", stack[top]
}

bool ISEMPTY() {
    Return top == -1
}


pseudo code for linked list implementation:

// Node structure for linked list
struct Node {
    int data
    Node* next
}

// Initialize top pointer
Node* top = NULL

// Push operation
void PUSH(element) {
    Create a new node (newNode)
    If newNode == NULL {
         Print "Failed to allocate memory for the new node"
        Return
    }
    newNode->data = element
    newNode->next = top
    top = newNode
}

// Pop operation
void POP() {
    If top == NULL {
        Print "Stack is empty. Unable to pop."
        Return
    }
    Print "Popped element:", top->data
    Node* temp = top
    top = top->next
    Free(temp)
}

// Peek operation
void PEEK() {
    If top == NULL {
        Print "Stack is empty"
        Return
    }
    Print "Top element in the stack:", top->data
}

// IsEmpty operation
bool ISEMPTY() {
    Return top == NULL
}

A queue follows the FIFO (First In, First Out) principle. The first element inserted into the queue is the first one to be removed.

Operations:
Enqueue(x): Add an element x to the rear of the queue.
Dequeue(): Remove the front element from the queue.
Front(): Get the front element of the queue without removing it.
isEmpty(): Check if the queue is empty. 

pseudo code for array implementation:

Initialize queue[MAX_SIZE], front = 0, and rear = -1

//to add value
void ENQUEUE(element) {
    If rear == MAX_SIZE - 1{
        Print "Queue Overflow"
        Return
    }
    Increment rear by 1
    queue[rear] = element
}

//to remove value
void DEQUEUE() {
    If front > rear{
        Print "Queue Underflow"
        Return
    }
    Print "Dequeued element:", queue[front]
    Increment front by 1
}

void FRONT() {
    If front > rear{
        Print "Queue is empty"
        Return
    }
    Print "Front element:", queue[front]
}

bool ISEMPTY() {
    Return front > rear
}

pseudo code for linked list implementation:

// Node structure for linked list
struct Node {
    int data
    Node* next
}

// Initialize front and rear pointers
Node* front = NULL
Node* rear = NULL

// Enqueue operation
void ENQUEUE(element) {
    Create a new node (newNode)
    If newNode == NULL {
        Print "Failed to allocate memory for the new node"
        Return
    }
    newNode->data = element
    newNode->next = NULL
    If rear == NULL {
        front = rear = newNode
    } Else {
        rear->next = newNode
        rear = newNode
    }
}

// Dequeue operation
void DEQUEUE() {
    If front == NULL {
        Print "Queue is empty. Unable to dequeue."
        Return
    }
    Print "Element dequeued from queue:", front->data
    Node* temp = front
    front = front->next
    If front == NULL {
        rear = NULL
    }
    Free(temp)
}

// Front operation
void FRONT() {
    If front == NULL {
        Print "Queue is empty. No front element available."
        Return
    }
    Print "Front element in the queue:", front->data
}

// IsEmpty operation
bool ISEMPTY() {
    Return front == NULL
}


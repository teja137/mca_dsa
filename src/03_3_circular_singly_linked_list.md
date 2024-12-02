void CREATE_NODE(value) {
    Create a new node
    Set the node's data to value
    Set the node's next pointer to itself (since it's circular)
    Return the new node
}

void INSERT_AT_BEGINNING(head, value) {
    Create a new node with value
    If head is NULL {
        Set the new node's next pointer to itself
        Set head to the new node
        Return head
    }
    Traverse the list to find the last node (where node->next == head)
    Set the new node's next pointer to head
    Set the last node's next pointer to the new node
    Set head to the new node
    Return head
}

void INSERT_AT_END(head, value) {
    Create a new node with value
    If head is NULL {
        Set the new node's next pointer to itself
        Set head to the new node
        Return head
    }
    Traverse the list to find the last node (where node->next == head)
    Set the last node's next pointer to the new node
    Set the new node's next pointer to head
    Return head
}

void DELETE_FROM_BEGINNING(head) {
    If head is NULL {
        Print "List is empty"
        Return NULL
    }
    If head->next == head { // Only one node in the list
        Delete head
        Return NULL
    }
    Traverse the list to find the last node (where node->next == head)
    Set the last node's next pointer to head->next
    Move head to head->next
    Delete the old head
    Return new head
}

void DELETE_FROM_END(head) {
    If head is NULL {
        Print "List is empty"
        Return NULL
    }
    If head->next == head { // Only one node in the list
        Delete head
        Return NULL
    }
    Traverse the list to find the second last node (where node->next->next == head)
    Set the second last node's next pointer to head
    Delete the last node
    Return head
}

**List Array**

we have 2 lists

1. ordered list:

means ascending or descending or items repeat like 10,5,15,30,20 or 2,4,6,8,10 

2. unordered list:

no specific order. Wherever you want you can insert or deleted data.

----------------------------------------


ordered list array implementation

# basic looping and adding or deleting

--------------------------------------------

primitive data structures - int, char, float

non - primitive data structures
        - linear data structure
            - list, stack, que, linked list
        - non linear data structure
            tree, graph

-------------------------------------------------

List is a collection of items.

continuous memory order - insertion or deletion of data becomes difficult but easy to read. ed: array

discontinuous memory locations - insertion or deletion easy. ex: linked list

Its like

List
Singly linked list
Doubly linked list
Circular linked list


**linked list**

It is a dynamic data structure. It is a collection of nodes

It is a dynamic representation of list.

You can allocate memory whenever you want, you can deallocate memory whenever you don't want.
If we don't know exact size of the array then go for linked list data structure. 
you can increase or decrease the size during run time.

when dealing with unknown input or when input is constantly changing, we can use linked list

disadvantage:
it takes double the size of the given input. It takes more memory.
-----

this how linked list looks:

node:
[data field][address field or next address]
[head node][tail node]

syntax:

keyword is struct
it takes 2 inputs: dada field and address field

*singly
struct NODE{
    int data;
    struct NODE*next;
}

*doubly
struct NODE{
    int data;
    struct NODE*next;
    struct NODE*previous;
}

we have 4 types of linked lists:

Singly linear linked list - it has 2 fields [data][next address], if tail node is null is called linear
Singly circular linked list - it has 2 fields [data][next address], if tail node is linked to address of fist node is called circular
Doubly linear linked list - it has 3 fields [data][next address][previous address], if first node previous field is null and tail node next field is null is called linear
Doubly circular linked list - it has 3 fields [data][next address][previous address], if first node previous field is filled with address of last node and if tail node next field is linked to address of fist node


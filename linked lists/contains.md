# Contains

## Prerequisites
Pointers; Loops; Functions; Structures

## Problem
Write a function that returns true if a node in the linked list contains int i and false otherwise. Expected output:
```c
jharvard@run.cs50.net (~): ./a.out
What value are you looking for? 9
Sorry, the list only contains 1 2 3 4 5
```

## Distribution Code
```c
#include <cs50.h>
#include <stdbool.h>
#include <stdio.h>
#include <stdlib.h>

#define SIZE 5

typedef struct node
{
    // the value to store in this node
    int n;

    // the link to the next node in the list
    struct node* next;
}
node;

node* head = NULL;

bool contains(int i)
{
    // TODO
}

int main(void)
{
    // create linked list
    for (int i = SIZE; i > 0; i--)
    {
        node* new = malloc(sizeof(node));

        if (new == NULL)
        {
            exit(1);
        }
        new->n = i;
        new->next = head;
        head = new;
    }

    printf("What value are you looking for? ");
    int i = get_int();

    if (contains(i))
    {
        printf("Found it! The list contains ");
    }
    else
    {
        printf("Sorry, the list only contains ");
    }
    for (node*  ptr = head; ptr != NULL; ptr = ptr->next)
    {
        printf("%i ", ptr->n);
    }
    printf("\n");
}
```
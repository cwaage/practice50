# Search

## Prerequisites
Pointers; Recursion; Functions; Binary Search

## Problem
Write a function called search with a prototype of <code>bool search (node* root, int val);</code> that returns <code>true</code> if the binary search tree pointed to by root contains <code>val</code>, and <code>false</code> otherwise. Expected output:

```c
jharvard@run.cs50.net (~): ./a.out
Tree contains 6? true
Tree contains 10? false
Tree contains 1? false
Tree contains 9? true
```

## Distribution Code
```c
#include <stdbool.h>
#include <stdio.h>
#include <stdlib.h>

typedef struct node
{
    int n;
    struct node* left;
    struct node* right;
}
node;

node* root;

bool search(node* r, int val)
{
    // TODO
}

int main(void)
{
    // create root node
    root = malloc(sizeof(node));
    if (root == NULL)
    {
        printf("Out of memory!\n");
        return 1;
    }
    root->n = 7;
    root->left = NULL;
    root->right = NULL;
    
    // create more nodes
    node* three = malloc(sizeof(node));
    if (three == NULL)
    {
        printf("Out of memory!\n");
        return 1;
    }
    three->n = 3; 
    three->left = NULL;
    three->right = NULL;
    
    node* six = malloc(sizeof(node));
    if (six == NULL)
    {
        printf("Out of memory!\n");
        return 1;
    }
    six->n = 6;
    six->left = NULL;
    six->right = NULL;
    
    node* nine = malloc(sizeof(node));
    if (nine == NULL)
    {
        printf("Out of memory!\n");
        return 1;
    }
    nine->n = 9;
    nine->left = NULL;
    nine->right = NULL;

    // link together nodes
    root->left = three;
    root->right = nine;
    three->right = six; 
    
    // testing contains
    printf("Tree contains 6? %s\n", search(root, 6)? "true" : "false"); 
    printf("Tree contains 10? %s\n", search(root, 10)? "true" : "false");
    printf("Tree contains 1? %s\n", search(root, 1)? "true" : "false");
    printf("Tree contains 9? %s\n", search(root, 9)? "true" : "false");  
    
    return 0;
}
```
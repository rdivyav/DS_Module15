# Ex12 Binary Search Tree
## DATE:28.4.2025
## AIM:
To write a C function to insert the elements in the binary search tree

## Algorithm
1.Start at the root 
2.Compare and move 
3.Repeat comparison 
4.Insert the new node  
5.Return the root   

## Program:
```
/*
Program to insert the elements in the binary search tree
Developed by: Divya R V
RegisterNumber:212223100005  
*/
```
```
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>
 
struct node {
    
    int data;
    struct node *left;
    struct node *right;
  
};
 
void preOrder( struct node *root) {
  
    if( root == NULL ) 
      return;
    printf("%d ",root->data);
    preOrder(root->left);
    preOrder(root->right);
  
}
 
/* you only have to complete the function given below.  
node is defined as  
 
struct node {
    
    int data;
    struct node *left;
    struct node *right;
  
};
 
*/
void search(struct node*);
struct node *temp;
struct node* insert( struct node* root, int data ) 
{
    temp=(struct node*)malloc(1*sizeof(struct node));
    temp->data=data;
    temp->left=temp->right=NULL;
    if(root==NULL)
    {
        root=temp;
    }
    else
    {
        search(root);
    }
    
   return root; 
}
void search(struct node *t)
{
   if ((temp->data > t->data) && (t->right != NULL))      /* value more than root node value insert at right */
       search(t->right);
   else if ((temp->data > t->data) && (t->right == NULL))
       t->right = temp;
   else if ((temp->data < t->data) && (t->left != NULL))    /* value less than root node value insert at left */
       search(t->left);
   else if ((temp->data < t->data) && (t->left == NULL))
       t->left = temp;  
    
}
 
 
int main() {
  
    struct node* root = NULL;
    
    int t;
    int data;
 
    scanf("%d", &t);
 
    while(t-- > 0) {
        scanf("%d", &data);
        root = insert(root, data);
    }
  
    preOrder(root);
    return 0;
}

```
## Output:

![Screenshot 2025-04-29 095245](https://github.com/user-attachments/assets/20a80854-4c93-4de1-985c-e4a93980ab58)


## Result:
Thus, the C function to insert the elements in the binary search tree is implemented successfully.

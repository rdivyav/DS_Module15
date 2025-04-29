# Ex11 Tree Representation and Traversal
## DATE:28.4.2025
## AIM:
To write a C function to perform post order traversal of a binary tree.

## Algorithm
1.Check for an empty node 
2.Traverse the left subtree 
3.Traverse the right subtree 
4.Visit the current node  
5.Return   

## Program:
```
/*
Program to perform post order traversal of a binary tree.
Developed by:Divya R V 
RegisterNumber: 212223100005 
*/
```
```
#include <stdio.h>

#include <stdlib.h>

struct node {
    
    int data;
    struct node *left;
    struct node *right;
  
};

struct node* insert( struct node* root, int x ) {
	struct node* newnode ;
	newnode = (struct node*)malloc(sizeof(struct node));	
	if(root == NULL) 
	{
        newnode->data = x;
        newnode->left = NULL;
        newnode->right = NULL;
        return newnode;
	  
	}
	else 
	{
		if(x<root->data) 
		{
             root->left =insert(root->left, x);
           
		}
		else if(x>root->data)
		{
           root->right = insert(root->right, x);
		}
	
		return root;
	}
}

/* you only have to complete the function given below.  
node is defined as  

struct node {
    
    int data;
    struct node *left;
    struct node *right;
  
};

*/
void postOrder( struct node *root) 
{
if(root==NULL)
{
    return;
}
else
{
    postOrder(root->left);
    postOrder(root->right);
    printf("%d ",root->data);
}

}

int main() {
  
    struct node* root = NULL;
  int i,n,input;
  scanf("%d",&n);
  for(i=0;i<n;i++)
  {
      scanf("%d",&input);
      root=insert(root,input);
  }
	postOrder(root);
    return 0;
}

```
## Output:

![Screenshot 2025-04-29 094706](https://github.com/user-attachments/assets/697bf172-8e09-40db-85c4-5ce607b1bb98)


## Result:
Thus, the function to perform post order traversal of a binary tree is implemented successfully

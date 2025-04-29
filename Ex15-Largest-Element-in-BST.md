# Ex15 Largest Element in BST
## DATE:28.4.25
## AIM:
To Write a c program to find the largest value in a Binary Search Tree.

## Algorithm
1.Start at the root node 
2.Check for an empty tree 
3.Traverse to the rightmost node 
4.Repeat until the right child is NULL  
5.Return the value   

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by:Divya RV 
RegisterNumber: 212223100005 
*/
```
```
void postOrder( struct node *root) {
  
    if(root==NULL)
    {
        return ;
    }
    postOrder(root->left);
    postOrder(root->right);
    printf("%d ",root->data);
  
}
```
## Output:

![Screenshot 2025-04-29 115208](https://github.com/user-attachments/assets/c3fb4e21-e10f-493c-9bf2-f8a5a5673483)


## Result:
Thus, the C program to find the largest value in a Binary Search Tree is implemented successfully.

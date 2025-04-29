# Ex13 Expression Tree
## DATE:28.4.2025
## AIM:
To write a C function to construct an Expression Tree for the given Postfix Expression and display the output in the format of In-order ,Pre-order and Post-order traversal.

## Algorithm
1. Constructing the Expression Tree
2. Inorder Traversal 
3. Preorder Traversal
4. Postorder Traversal 
5.Displaying the Output   

## Program:
```
/*
Program to construct an Expression Tree for the given Postfix Expression and display the output in the format of In-order ,Pre-order and Post-order traversal.
Developed by:Divya R V 
RegisterNumber:212223100005  
*/
```
```
#include <stdio.h>
#include<stdlib.h>
struct n {
   char d;
   struct n *l;
   struct n *r;
};
char pf[50];
int top = -1;
struct n *a[50];
int r(char inputch) {
   if (inputch == '+' || inputch == '-' || inputch == '*' || inputch== '/')
      return (-1);
   else if (inputch >= 'A' || inputch <= 'Z')
      return (1);
   else if (inputch >= 'a' || inputch <= 'z')
      return (1);
   else
      return (-100);
}
void push(struct n *tree) {
   top++;
   a[top] = tree;
}
struct n *pop() {
   top--;
   return (a[top + 1]);
}
void construct_expression_tree(char *suffix) {
   char s;
   struct n *newl, *p1, *p2;
   int flag;
   s = suffix[0];
   for (int i = 1; s != 0; i++) {
      flag = r(s);
      if (flag == 1) {
         newl=(struct n *)malloc(1*sizeof(struct n));

         newl->d = s;
         newl->l = NULL;
         newl->r = NULL;
         push(newl);
      } else {
         p1 = pop();
         p2 = pop();
         newl=(struct n *)malloc(1*sizeof(struct n));
         newl->d = s;
         newl->l = p2;
         newl->r = p1;
         push(newl);
      }
      s = suffix[i];
   }
}
void preOrder(struct n *tree) {
   if(tree==NULL)
   {
       return ;
   }
  
   
       printf("%c",tree->d);
       preOrder(tree->l);
       preOrder(tree->r);
   
}
void inOrder(struct n *tree) {
  if(tree==NULL)
  {
      return ;
  }
  
  
      inOrder(tree->l);
      printf("%c",tree->d);
      inOrder(tree->r);
      
  
}
void postOrder(struct n *tree) {
   if(tree==NULL)
   {
       return ;
   }

       postOrder(tree->l);
       postOrder(tree->r);
       printf("%c",tree->d);
       
   
}
int main() {
 
   scanf("%s",pf);
   construct_expression_tree(pf);
  // printf("\nIn-Order Traversal : ");
   inOrder(a[0]);
   printf("\n");
   //printf("\nPre-Order Traversal : ");
   preOrder(a[0]);
   printf("\n");
   //printf("\nPost-Order Traversal : ");
   postOrder(a[0]);
   printf("\n");
   return 0;
}

```
## Output:

![Screenshot 2025-04-29 100433](https://github.com/user-attachments/assets/0f405af1-71bc-4c05-b46a-8b7d0185c39b)


## Result:
Thus, the C program to display the Expression Tree in the format of In-order ,Pre-order and Post-order traversal.

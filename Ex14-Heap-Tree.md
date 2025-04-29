# Ex14 Heap Tree
## DATE:28.4.2025
## AIM:
To write a C function to delete an element in a Heap Tree.

## Algorithm
1.Replace the root with the last element 
2.Remove the last element 
3. Heapify 
4.If not the root, swap  
5.Decrement heap size   

## Program:
```
/*
Program to delete an element in a Heap Tree
Developed by:Divya R V 
RegisterNumber: 212223100005 
*/
```
```
#include <stdio.h>
int size = 0;
void swap(int *a, int *b)
{
  int temp = *b;
  *b = *a;
  *a = temp;
}
void heapify(int array[], int size, int i)
{
  if (size == 1)
  {
    printf("Single element in the heap");
  }
  else
  {
    int largest = i;
    int l = 2 * i + 1;
    int r = 2 * i + 2;
    if (l < size && array[l] > array[largest])
      largest = l;
    if (r < size && array[r] > array[largest])
      largest = r;
    if (largest != i)
    {
      swap(&array[i], &array[largest]);
      heapify(array, size, largest);
    }
  }
}
void insert(int array[], int newNum)
{
  if (size == 0)
  {
    array[0] = newNum;
    size += 1;
  }
  else
  {
    array[size] = newNum;
    size += 1;
    for (int i = size / 2 - 1; i >= 0; i--)
    {
      heapify(array, size, i);
    }
  }
}
void deleteRoot(int array[], int num)
{
    int i;
    for(i=0 ;i<size;i++)
    {
        if(array[i]==num)
        {
        break;
        }
    }
       
            swap(&array[i],&array[size-1]);
            size--;

        for( i=size/2-1;i>=0;i--)
        {
        heapify(array, size, i);
        }
        
 }
  

void printArray(int array[], int size)
{
  for (int i = 0; i < size; i++)
    printf("%d ", array[i]);
  printf("\n");
}
int main()
{
  int array[10],n,data,x;
  scanf("%d",&n);
  for(int i=0;i<n;i++)
  {
      scanf("%d",&data);
      insert(array, data);
  }

  //printf("Max-Heap array: ");
  //printArray(array, size);
  scanf("%d",&x);

  deleteRoot(array, x);

  printf("After deleting an element: ");

  printArray(array, size);
}
```
## Output:

![Screenshot 2025-04-29 114714](https://github.com/user-attachments/assets/e662cb40-43d3-4820-8d1b-8494d7ce662c)


## Result:
Thus, the function to delete an element in a Heap Tree is implemented successfully.

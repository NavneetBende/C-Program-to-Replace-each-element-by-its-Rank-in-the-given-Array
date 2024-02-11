Replace each element by its rank given in array in C
In this article, we will brief in on how to replace each element by its rank in the given array using C language. There is an array of n elements, replace each element of the array by its corresponding rank. The minimum value element will have the highest rank.

Replace each element by its rank given in array in C
While loop in C
What do you mean by rank?
The rank of an element is defined as the distance between the element with the first element of the array when the array is arranged in ascending order.
If two or more are same in the array then their rank is also the same as the rank of the first occurrence of the element.
Example :
Input : arr[5] = {100, 2, 70, 12, 90}
Rank of 100 is 5
Rank of 2 is 1
Rank of 70 is 3
Rank of 12 is 2
Rank of 90 is 4
Output : 5 1 3 2 4
Algorithm :
Create a copy of the given input array.
Sort the copied array.
Run a nested loop and find the position of the given array element in the sorted array.
And replace the element with the position.
Print the modified input array.
Time and Space Complexity:
Time Complexity : O(n2)
Space Complexity : O(n)
Code in C++
//Write a program to Replace each element by its rank given in array in C
#include<stdio.h>

int main(){
    int arr[] = { 100, 2, 70, 12 , 90};
    int n = sizeof(arr) / sizeof(arr[0]);
    
    int temp[n];
    for(int i=0; i<n; i++)
    temp[i] = arr[i];
    
    //sort the copied array
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
            int x = temp[i];
            temp[i] = temp[j];
            temp[j] = x;
        }
    }
    
    for(int i=0; i<n; i++){
    
        for(int j=0; j<n; j++){
            if(temp[j]==arr[i])
            {
                arr[i] = j+1;
                break;
            }
        }
    }
    
    for(int i=0; i<n; i++)
    printf("%d ", arr[i]);
}
Output
5 1 3 2 4

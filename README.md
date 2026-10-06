# day-8-c

1. Write a C program to dynamically allocate memory for n integers using calloc(), read the elements, and find the largest and smallest elements.
   
#include <stdio.h>
#include <stdlib.h>
int main() {
    int n, i;
    int *a;
    int largest, smallest;
    printf("Enter number of elements: ");
    scanf("%d", &n);
    a = (int *)calloc(n, sizeof(int));
    printf("Enter %d elements:\n", n);
    for (i = 0; i < n; i++) {
        scanf("%d", &a[i]);
    }
    largest = smallest = a[0];
    for (i = 1; i < n; i++) {
        if (a[i] > largest)
            largest = a[i];
        if (a[i] < smallest)
            smallest = a[i];
    }
    printf("Largest = %d\n", largest);
    printf("Smallest = %d\n", smallest);
    free(a);
    return 0;
}


2. Write a C program to dynamically allocate memory for an array of integers using malloc(). Increase the size of the array using realloc(), add new elements, and display all the elements.

#include <stdio.h>
#include <stdlib.h>
int main() {
    int n, newn, i;
    int *a;
    printf("Enter initial size: ");
    scanf("%d", &n);
    a = (int *)malloc(n * sizeof(int));
    printf("Enter %d elements:\n", n);
    for (i = 0; i < n; i++) {
        scanf("%d", &a[i]);
    }
    printf("Enter new size: ");
    scanf("%d", &newn);
    a = (int *)realloc(a, newn * sizeof(int));
    printf("Enter %d new elements:\n", newn - n);
    for (i = n; i < newn; i++) {
        scanf("%d", &a[i]);
    }
    printf("All elements:\n");
    for (i = 0; i < newn; i++) {
        printf("%d ", a[i]);
    }
    free(a);
    return 0;
}

3.Write a C program to dynamically allocate memory for n integers using malloc(), read the elements, and find their sum and average.

#include <stdio.h>
#include <stdlib.h>
int main() {
    int n, i;
    int *a;
    int sum = 0;
    float average;
    printf("Enter number of elements: ");
    scanf("%d", &n);
    a = (int *)malloc(n * sizeof(int));
    printf("Enter %d elements:\n", n);
    for (i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum = sum + a[i];
    }
    average = (float)sum / n;
    printf("Sum = %d\n", sum);
    printf("Average = %.2f\n", average);
    free(a);
    return 0;
}

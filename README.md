#include <stdio.h>

// Function to calculate average using pointer
float calculateAverage(int *marks, int n) {
    int sum = 0;
    for(int i = 0; i < n; i++) {
        sum += *(marks + i); // pointer arithmetic
    }
    return (float)sum / n;
}

// Function to find maximum marks using pointer
int findMax(int *marks, int n) {
    int max = *marks;
    for(int i = 1; i < n; i++) {
        if(*(marks + i) > max) {
            max = *(marks + i);
        }
    }
    return max;
}

// Function to find minimum marks using pointer
int findMin(int *marks, int n) {
    int min = *marks;
    for(int i = 1; i < n; i++) {
        if(*(marks + i) < min) {
            min = *(marks + i);
        }
    }
    return min;
}

int main() {
    int n;

    printf("Enter number of subjects: ");
    scanf("%d", &n);

    int marks[n];  

    printf("Enter marks of %d subjects:\n", n);
    for(int i = 0; i < n; i++) {
        scanf("%d", &marks[i]);
    }

    // Function calls using pointer
    float avg = calculateAverage(marks, n);
    int max = findMax(marks, n);
    int min = findMin(marks, n);

    printf("\n--- Student Marks Calculator ---\n");
    printf("Average Marks : %.2f\n", avg);
    printf("Maximum Marks : %d\n", max);
    printf("Minimum Marks : %d\n", min);

    return 0;
}
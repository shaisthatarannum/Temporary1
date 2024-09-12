# Temporary1

#include <stdio.h>

int main() {
    int n = 0;

    printf("ENTER SIZE OF ARRAY: ");
    scanf("%d", &n);

    int arr[n];
    int arrc[n];

    printf("ENTER %d ELEMENTS: ", n);

    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    // Copy elements to arrc
    for (int i = 0; i < n; i++) {
        arrc[i] = arr[i];
    }

    // Sort arrc using bubble sort
    int temp = 0;
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            if (arrc[i] > arrc[j]) {
                temp = arrc[i];
                arrc[i] = arrc[j];
                arrc[j] = temp;
            }
        }
    }

    // Create a visited array to track which sorted indices are already used
    int visited[n]; 
    for (int i = 0; i < n; i++) {
        visited[i] = 0;  // Initialize all as not visited
    }

    // Iterate original array and find its index in sorted array (arrc)
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            if (arr[i] == arrc[j] && visited[j] == 0) {  // Check if not visited
                arr[i] = j;  // Assign the index
                visited[j] = 1;  // Mark this index as visited
                break;
            }
        }
    }

    // Print the result
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }

    return 0;
}

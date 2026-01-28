# c-question-
Write a C++ program to read and display elements of an array.
```
#include <iostream>
#include <vector> // Using vector is often more modern/flexible, but a fixed-size array works too.

int main() {
    // 1. Declare the array size and the array
    const int SIZE = 5;
    int numbers[SIZE];

    std::cout << "Enter " << SIZE << " integers:" << std::endl;

    // 2. Read input into the array using a loop
    for (int i = 0; i < SIZE; ++i) {
        std::cout << "Element " << i << ": ";
        std::cin >> numbers[i];
    }

    std::cout << "\nYou entered the following elements:" << std::endl;

    // 3. Display the elements of the array using a range-based for loop
    for (int num : numbers) {
        std::cout << num << " ";
    }

    std::cout << std::endl;

    return 0;
}

```
Write a C++ program to find the sum of all elements in an array.

```
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;
    int arr[100];

    cout << "Enter number of elements: ";
    cin >> n;

    cout << "Enter array elements:\n";
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
        sum += arr[i];
    }

    cout << "Sum of array elements = " << sum << endl;

    return 0;
}
```
Write a C++ program to copy one array into another.
```
#include <iostream>
using namespace std;

int main() {
    int n;
    int arr1[100], arr2[100];

    cout << "Enter number of elements: ";
    cin >> n;

    cout << "Enter elements of first array:\n";
    for (int i = 0; i < n; i++) {
        cin >> arr1[i];
    }

    // Copying array
    for (int i = 0; i < n; i++) {
        arr2[i] = arr1[i];
    }

    cout << "Elements of second array after copying:\n";
    for (int i = 0; i < n; i++) {
        cout << arr2[i] << " ";
    }

    return 0;
}
```

Write a C++ program to print array elements at even index positions.
```
#include <iostream>
using namespace std;

int main() {
    int n;
    int arr1[100], arr2[100];

    cout << "Enter number of elements: ";
    cin >> n;

    cout << "Enter elements of the first array:\n";
    for (int i = 0; i < n; i++) {
        cin >> arr1[i];
    }

    // Copy elements from arr1 to arr2
    for (int i = 0; i < n; i++) {
        arr2[i] = arr1[i];
    }

    cout << "Elements of the second array after copying:\n";
    for (int i = 0; i < n; i++) {
        cout << arr2[i] << " ";
    }

    return 0;
}
```
Write a C++ program to read and display a 2D array (matrix).
```
#include <iostream>
using namespace std;

int main() {
    int rows, cols;
    int matrix[10][10];

    cout << "Enter number of rows and columns: ";
    cin >> rows >> cols;

    cout << "Enter elements of the matrix:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cin >> matrix[i][j];
        }
    }

    cout << "Matrix elements are:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

Write a C++ program to print all elements of a matrix in row-wise order.
```
#include <iostream>
using namespace std;

int main() {
    int rows, cols;
    int matrix[10][10];

    cout << "Enter number of rows and columns: ";
    cin >> rows >> cols;

    cout << "Enter elements of the matrix:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cin >> matrix[i][j];
        }
    }

    cout << "Matrix elements in row-wise order:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```
Write a C++ program to print all elements of a matrix in column-wise order.
```
#include <iostream>
using namespace std;

int main() {
    int rows, cols;
    int matrix[10][10];

    cout << "Enter number of rows and columns: ";
    cin >> rows >> cols;

    cout << "Enter elements of the matrix:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cin >> matrix[i][j];
        }
    }

    cout << "Matrix elements in column-wise order:\n";
    for (int j = 0; j < cols; j++) {
        for (int i = 0; i < rows; i++) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

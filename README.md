# C Programming: Pointers, Structures, and Memory Mapping
## ​1. Pointer Arithmetic & Dereferencing
​Understanding how pointers navigate memory addresses.
​Pointer Notation vs. Array Notation: Learning that a[i] is equivalent to *(a + i).
​Scaling: How ptr + 1 moves the address based on the sizeof the data type it points to.
​Double Pointers: Managing arrays of strings (char *str[]) where each element is a pointer to the first character of a string literal.
## ​2. Structures (User-Defined Data Types)
​Declaration & Initialization: Defining struct templates and initializing them with nested values.
​Memory Padding & Alignment: Calculating the sizeof a structure (e.g., why a struct with a char and an int might be larger than the sum of its parts).
​Self-Referential Structures: Using pointers within a struct to point to another instance of the same struct (the foundation of Linked Lists).
## ​3. Advanced Structure Access
​Dot (.) vs. Arrow (->) Operators: * Use . when accessing members from a structure variable.
​Use -> when accessing members via a pointer to a structure.
​Nested Structures: Accessing members inside a struct that is itself a member of another struct (e.g., S2.ss1.str).
## 4. Function Call Mechanisms
​Call by Value: Passing a copy of the structure to a function. Changes made inside the function do not affect the original variable.
​Call by Reference: Passing the address of a structure using pointers (&S). This allows the function to modify the original data.
## ​5. Memory Visualization
​In-depth analysis of how data is stored in RAM:
​String Literals: Stored in the Read-Only Data Segment; pointers hold their starting addresses.
​Stack Allocation: How local variables and structure instances are laid out in the stack frame.
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
1.
Create a structure Student with:

roll number

name

marks

Input details of 5 students and display students who scored more than 75 marks.
```
#include <iostream>
using namespace std;

struct Student {
    int roll;
    string name;
    float marks;
};

int main() {
    Student s[5];

    // Input details
    for (int i = 0; i < 5; i++) {
        cout << "\nEnter details of student " << i + 1 << endl;
        cout << "Roll Number: ";
        cin >> s[i].roll;
        cout << "Name: ";
        cin >> s[i].name;
        cout << "Marks: ";
        cin >> s[i].marks;
    }

    // Display students with marks > 75
    cout << "\nStudents who scored more than 75 marks:\n";
    for (int i = 0; i < 5; i++) {
        if (s[i].marks > 75) {
            cout << "Roll: " << s[i].roll
                 << ", Name: " << s[i].name
                 << ", Marks: " << s[i].marks << endl;
        }
    }

    return 0;
}
```


2.

Define a structure Employee containing:

employee ID

name

basic salary

Calculate and display gross salary (basic + 20% HRA + 10% DA).
```
#include <iostream>
using namespace std;

struct Employee {
    int empId;
    string name;
    float basic, gross;
};

int main() {
    Employee e;

    // Input details
    cout << "Enter Employee ID: ";
    cin >> e.empId;
    cout << "Enter Name: ";
    cin >> e.name;
    cout << "Enter Basic Salary: ";
    cin >> e.basic;

    // Gross salary calculation
    e.gross = e.basic + (0.20 * e.basic) + (0.10 * e.basic);

    // Output
    cout << "\nEmployee Details\n";
    cout << "ID: " << e.empId << endl;
    cout << "Name: " << e.name << endl;
    cout << "Gross Salary: " << e.gross << endl;

    return 0;
}
```

output question 
```
int arr[] = {10, 20, 30, 40};
int *p = arr;

cout << *p << endl;
cout << *(p + 1) << endl;
cout << *(p + 3) << endl;
```
```
int arr[] = {5, 10, 15, 20};
int *p = arr + 2;

cout << *p << endl;
cout << *(p - 1) << endl;
```
```
int arr[5] = {1, 2, 3, 4, 5};

for(int i = 0; i < 5; i++)
    cout << *(arr + i) << " ";
```
```
int arr[] = {2, 4, 6, 8};
int *p = arr;

p++;

cout << *p << endl;
```
```
int arr[] = {7, 14, 21};

cout << arr[1] << endl;
cout << 1[arr] << endl;
```
```
int arr[] = {7, 14, 21};

cout << arr[1] << endl;
cout << 1[arr] << endl;
```
```
int arr[] = {10, 20, 30};
int *p = arr;

cout << *p + 1 << endl;
cout << *(p + 1) << endl;
```
```
int arr[] = {3, 6, 9, 12};
int *p = arr;

while(p <= &arr[3]) {
    cout << *p << " ";
    p++;
}
```
```
int arr[] = {1, 2, 3};
int *p = arr;

for(int i = 0; i < 3; i++)
    cout << *(p++) << " ";
```
```
int arr[] = {10, 20, 30};
int *p = arr;

cout << p << endl;
cout << p + 1 << endl;
```
```
char arr[] = {'A', 'B', 'C'};
char *p = arr;

cout << p << endl;
cout << p + 1 << endl;
```
```
struct Data {
    int x;
    int y;
};

Data arr[] = {{1,2}, {3,4}, {5,6}};
Data *p = arr;

cout << p->x << endl;
cout << (p + 1)->y << endl;
```
```
struct Item {
    int price;
};

Item arr[] = {100, 200, 300};
Item *p = arr;

cout << p[2].price << endl;
cout << (*(p + 1)).price << endl;
```

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
10
20
40
```
```
int arr[] = {5, 10, 15, 20};
int *p = arr + 2;

cout << *p << endl;
cout << *(p - 1) << endl;
```
```
15
10
```
```
int arr[5] = {1, 2, 3, 4, 5};

for(int i = 0; i < 5; i++)
    cout << *(arr + i) << " ";

```
1
2
3
4
5
```
int arr[] = {2, 4, 6, 8};
int *p = arr;

p++;

cout << *p << endl;
```
```
4
```
```
int arr[] = {7, 14, 21};

cout << arr[1] << endl;
cout << 1[arr] << endl;
```
```
14
14
```

```
int arr[] = {10, 20, 30};
int *p = arr;

cout << *p + 1 << endl;
cout << *(p + 1) << endl;
```
```
11
20
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
3
6
9
12
```
```
int arr[] = {1, 2, 3};
int *p = arr;

for(int i = 0; i < 3; i++)
    cout << *(p++) << " ";
```
```
1
2
3
```
```
int arr[] = {10, 20, 30};
int *p = arr;

cout << p << endl;
cout << p + 1 << endl;
```
```
0x7ffee4b2a8c0
0x7ffee4b2a8c4

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
1
4
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

```
300
200
```
## Write a C++ program to implement a singly linked list using struct for the node and dynamic memory allocation with new and delete. Implement the following operations:

Insertion of a node at the beginning

Insertion of a node at the end

Deletion of a node

Display the entire list
Use new to allocate memory for each node, and delete to free memory when deleting nodes.
```
#include <iostream>
using namespace std;

// Structure for Node
struct Node {
    int data;
    Node* next;
};

// Function to insert at beginning
void insertAtBeginning(Node*& head, int value) {
    Node* newNode = new Node;     // Allocate memory
    newNode->data = value;
    newNode->next = head;
    head = newNode;

    cout << "Inserted at beginning.\n";
}

// Function to insert at end
void insertAtEnd(Node*& head, int value) {
    Node* newNode = new Node;     // Allocate memory
    newNode->data = value;
    newNode->next = NULL;

    if (head == NULL) {
        head = newNode;
    } else {
        Node* temp = head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }

    cout << "Inserted at end.\n";
}

// Function to delete a node by value
void deleteNode(Node*& head, int value) {
    if (head == NULL) {
        cout << "List is empty.\n";
        return;
    }

    Node* temp = head;
    Node* prev = NULL;

    // If head node needs to be deleted
    if (temp != NULL && temp->data == value) {
        head = temp->next;
        delete temp;              // Free memory
        cout << "Node deleted.\n";
        return;
    }

    // Search for the node to delete
    while (temp != NULL && temp->data != value) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        cout << "Value not found.\n";
        return;
    }

    prev->next = temp->next;
    delete temp;                  // Free memory
    cout << "Node deleted.\n";
}

// Function to display the list
void display(Node* head) {
    if (head == NULL) {
        cout << "List is empty.\n";
        return;
    }

    Node* temp = head;
    cout << "Linked List: ";
    while (temp != NULL) {
        cout << temp->data << " -> ";
        temp = temp->next;
    }
    cout << "NULL\n";
}

// Main function
int main() {
    Node* head = NULL;
    int choice, value;

    do {
        cout << "\n--- Singly Linked List Menu ---\n";
        cout << "1. Insert at Beginning\n";
        cout << "2. Insert at End\n";
        cout << "3. Delete a Node\n";
        cout << "4. Display List\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                cout << "Enter value: ";
                cin >> value;
                insertAtBeginning(head, value);
                break;

            case 2:
                cout << "Enter value: ";
                cin >> value;
                insertAtEnd(head, value);
                break;

            case 3:
                cout << "Enter value to delete: ";
                cin >> value;
                deleteNode(head, value);
                break;

            case 4:
                display(head);
                break;

            case 5:
                cout << "Exiting...\n";
                break;

            default:
                cout << "Invalid choice!\n";
        }

    } while (choice != 5);

    return 0;
}
```
## Write a C++ program that dynamically allocates memory for an array of strings (an array of pointers). The program should:

Allow the user to input multiple strings.

Print all the strings using the array of pointers.

Free the allocated memory for each string and the array of pointers using delete[].
```
#include <iostream>
#include <cstring>   // For strlen and strcpy
using namespace std;

int main() {
    int n;

    cout << "Enter number of strings: ";
    cin >> n;
    cin.ignore();   // Clear newline from input buffer

    // Dynamically allocate array of pointers
    char** arr = new char*[n];

    // Input strings
    for (int i = 0; i < n; i++) {
        char temp[100];  // Temporary buffer

        cout << "Enter string " << i + 1 << ": ";
        cin.getline(temp, 100);

        // Allocate exact memory for each string
        arr[i] = new char[strlen(temp) + 1];

        // Copy string into allocated memory
        strcpy(arr[i], temp);
    }

    // Display strings
    cout << "\nYou entered:\n";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << endl;
    }

    // Free memory for each string
    for (int i = 0; i < n; i++) {
        delete[] arr[i];
    }

    // Free memory for array of pointers
    delete[] arr;

    return 0;
}
```
## Swap Two Numbers Using Pointers
Write a C++ program that swaps two numbers using pointers. The program should:

Declare two integer variables.

Use a pointer to swap their values.

Print the swapped values.
```
#include <iostream>
using namespace std;

int main() {
    int a, b;

    cout << "Enter first number: ";
    cin >> a;

    cout << "Enter second number: ";
    cin >> b;

    // Declare pointers
    int* p1 = &a;
    int* p2 = &b;

    // Swap using pointers
    int temp = *p1;
    *p1 = *p2;
    *p2 = temp;

    cout << "\nAfter swapping:\n";
    cout << "First number: " << a << endl;
    cout << "Second number: " << b << endl;

    return 0;
}
```
##
Write a C++ program that dynamically allocates memory for an array of strings (an array of pointers). The program should:

Allow the user to input multiple strings.

Print all the strings using the array of pointers.

Free the allocated memory for each string and the array of pointers using delete[].
```
#include <iostream>
#include <cstring>
using namespace std;

int main() {
    int n;

    cout << "Enter number of strings: ";
    cin >> n;
    cin.ignore();  // Clear newline from buffer

    // Step 1: Allocate memory for array of pointers
    char** arr = new char*[n];

    // Step 2: Input strings
    for (int i = 0; i < n; i++) {
        char temp[100];   // Temporary buffer

        cout << "Enter string " << i + 1 << ": ";
        cin.getline(temp, 100);

        // Allocate exact memory for each string (+1 for '\0')
        arr[i] = new char[strlen(temp) + 1];

        // Copy string into dynamically allocated memory
        strcpy(arr[i], temp);
    }

    // Step 3: Print all strings
    cout << "\nYou entered:\n";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << endl;
    }

    // Step 4: Free memory for each string
    for (int i = 0; i < n; i++) {
        delete[] arr[i];
    }

    // Step 5: Free memory for array of pointers
    delete[] arr;

    return 0;
}
```
## Write a C++ program that implements a circular buffer using a dynamically allocated array. The program should:

Dynamically allocate memory for the buffer.

Allow the user to add and remove elements.

Handle overflow and underflow conditions.

Properly deallocate the memory used by the buffer.
```
#include <iostream>
using namespace std;

class CircularBuffer {
private:
    int* buffer;
    int size;
    int front;
    int rear;
    int count;

public:
    // Constructor: allocate memory
    CircularBuffer(int s) {
        size = s;
        buffer = new int[size];
        front = 0;
        rear = -1;
        count = 0;
    }

    // Add element (Enqueue)
    void enqueue(int value) {
        if (count == size) {
            cout << "Buffer Overflow! Cannot add element.\n";
            return;
        }

        rear = (rear + 1) % size;
        buffer[rear] = value;
        count++;
        cout << "Inserted: " << value << endl;
    }

    // Remove element (Dequeue)
    void dequeue() {
        if (count == 0) {
            cout << "Buffer Underflow! Nothing to remove.\n";
            return;
        }

        cout << "Removed: " << buffer[front] << endl;
        front = (front + 1) % size;
        count--;
    }

    // Display buffer
    void display() {
        if (count == 0) {
            cout << "Buffer is empty.\n";
            return;
        }

        cout << "Buffer elements: ";
        for (int i = 0; i < count; i++) {
            cout << buffer[(front + i) % size] << " ";
        }
        cout << endl;
    }

    // Destructor: free memory
    ~CircularBuffer() {
        delete[] buffer;
        cout << "Memory deallocated.\n";
    }
};

int main() {
    int size, choice, value;

    cout << "Enter buffer size: ";
    cin >> size;

    CircularBuffer cb(size);

    do {
        cout << "\n--- Circular Buffer Menu ---\n";
        cout << "1. Add Element\n";
        cout << "2. Remove Element\n";
        cout << "3. Display Buffer\n";
        cout << "4. Exit\n";
        cout << "Enter choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                cout << "Enter value: ";
                cin >> value;
                cb.enqueue(value);
                break;

            case 2:
                cb.dequeue();
                break;

            case 3:
                cb.display();
                break;

            case 4:
                cout << "Exiting...\n";
                break;

            default:
                cout << "Invalid choice!\n";
        }

    } while (choice != 4);

    return 0;
}
```
## Write a C++ program that demonstrates the use of a pointer to a constant variable. The program should:

Declare a constant variable and a pointer to it.

Show how you can read the value pointed to by the pointer, but not modify it.
```
#include <iostream>
using namespace std;

int main() {
    // Declare a constant variable
    const int number = 100;

    // Declare a pointer to a constant integer
    const int* ptr = &number;

    // Reading the value using pointer
    cout << "Value of number: " << number << endl;
    cout << "Value using pointer: " << *ptr << endl;

    // Attempt to modify the value (This will cause a compilation error)
    // *ptr = 200;   // ❌ Not allowed

    return 0;
}
```
## Write a C++ program where a function returns a reference to a local variable. What are  potential problems and how to avoid them. Implement a version where the function returns a reference to a static or globally declared variable.
```
#include <iostream>
using namespace std;

// Function returning reference to static variable
int& getStaticReference() {
    static int x = 10;   // Static variable persists after function ends
    return x;
}

int main() {
    int& ref = getStaticReference();
    cout << "Original value: " << ref << endl;

    // Modify through reference
    ref = 50;
    cout << "Modified value: " << getStaticReference() << endl; // 50
    return 0;
}
```
```
#include <iostream>
using namespace std;

int globalVar = 100;

int& getGlobalReference() {
    return globalVar;  // Safe
}

int main() {
    int& ref = getGlobalReference();
    cout << "Global value: " << ref << endl;

    ref = 200;  // Modifies the global variable
    cout << "Modified global value: " << globalVar << endl;
    return 0;
}
```

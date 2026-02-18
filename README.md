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
```
## Create a struct Subject { string name; int marks; }.
Create a class Student with:

private: int roll; string name; Subject* subjects; int n;

constructor allocates dynamic memory for n subjects

member functions: input(), display(), total(), grade()

Store N students using pointer to object array, find topper, and free all memory properly.
```
#include <iostream>
#include <string>
using namespace std;

struct Subject {
    string name;
    int marks;
};

class Student {
private:
    int roll;
    string name;
    Subject* subjects;
    int n;  // number of subjects

public:
    // Constructor
    Student(int numSubjects = 0) {
        n = numSubjects;
        if (n > 0)
            subjects = new Subject[n];
        else
            subjects = nullptr;
    }

    // Destructor
    ~Student() {
        delete[] subjects;
    }

    void input() {
        cout << "\nEnter Roll Number: ";
        cin >> roll;
        cout << "Enter Name: ";
        cin >> name;

        for (int i = 0; i < n; i++) {
            cout << "\nEnter Subject " << i + 1 << " Name: ";
            cin >> subjects[i].name;
            cout << "Enter Marks: ";
            cin >> subjects[i].marks;
        }
    }

    void display() const {
        cout << "\nRoll No: " << roll;
        cout << "\nName: " << name;
        cout << "\nSubjects:\n";

        for (int i = 0; i < n; i++) {
            cout << subjects[i].name << " : " << subjects[i].marks << endl;
        }

        cout << "Total Marks: " << total();
        cout << "\nGrade: " << grade() << endl;
    }

    int total() const {
        int sum = 0;
        for (int i = 0; i < n; i++) {
            sum += subjects[i].marks;
        }
        return sum;
    }

    char grade() const {
        float avg = (float)total() / n;

        if (avg >= 90) return 'A';
        else if (avg >= 75) return 'B';
        else if (avg >= 50) return 'C';
        else return 'F';
    }
};

int main() {
    int N, nSubjects;

    cout << "Enter number of students: ";
    cin >> N;

    cout << "Enter number of subjects per student: ";
    cin >> nSubjects;

    // Dynamic array of Student objects
    Student* students = new Student[N];

    // Reallocate each student with subject count
    for (int i = 0; i < N; i++) {
        students[i] = Student(nSubjects);
        cout << "\nEntering details for Student " << i + 1;
        students[i].input();
    }

    // Display all students
    cout << "\n\n--- Student Details ---\n";
    for (int i = 0; i < N; i++) {
        students[i].display();
    }

    // Find Topper
    int maxIndex = 0;
    for (int i = 1; i < N; i++) {
        if (students[i].total() > students[maxIndex].total()) {
            maxIndex = i;
        }
    }

    cout << "\n\n--- Topper ---\n";
    students[maxIndex].display();

    // Free memory
    delete[] students;

    return 0;
}
```
## Create a struct Node containing:

Patient data (id, name, severity)

Node* next

Create a class PatientQueue implementing:

enqueue (based on severity priority)

dequeue

display
Use dynamic memory (new/delete) and demonstrate queue operations.
```
#include <iostream>
#include <string>
using namespace std;

struct Node {
    int id;
    string name;
    int severity;   // Higher value = Higher priority
    Node* next;
};

class PatientQueue {
private:
    Node* front;

public:
    PatientQueue() {
        front = nullptr;
    }

    ~PatientQueue() {
        // Free all remaining nodes
        while (front != nullptr) {
            dequeue();
        }
    }

    // Enqueue based on severity (priority insertion)
    void enqueue(int id, string name, int severity) {
        Node* newNode = new Node;
        newNode->id = id;
        newNode->name = name;
        newNode->severity = severity;
        newNode->next = nullptr;

        // If queue is empty OR new node has higher priority than front
        if (front == nullptr || severity > front->severity) {
            newNode->next = front;
            front = newNode;
        }
        else {
            Node* temp = front;
            while (temp->next != nullptr && 
                   temp->next->severity >= severity) {
                temp = temp->next;
            }
            newNode->next = temp->next;
            temp->next = newNode;
        }

        cout << "Patient Enqueued Successfully!\n";
    }

    // Dequeue (remove highest priority patient)
    void dequeue() {
        if (front == nullptr) {
            cout << "Queue is empty!\n";
            return;
        }

        Node* temp = front;
        cout << "Dequeued Patient: "
             << temp->name << " (Severity: "
             << temp->severity << ")\n";

        front = front->next;
        delete temp;
    }

    // Display queue
    void display() {
        if (front == nullptr) {
            cout << "Queue is empty!\n";
            return;
        }

        Node* temp = front;
        cout << "\n--- Patient Queue ---\n";
        while (temp != nullptr) {
            cout << "ID: " << temp->id
                 << ", Name: " << temp->name
                 << ", Severity: " << temp->severity
                 << endl;
            temp = temp->next;
        }
    }
};

int main() {
    PatientQueue pq;

    // Demonstration
    pq.enqueue(101, "Alice", 2);
    pq.enqueue(102, "Bob", 5);
    pq.enqueue(103, "Charlie", 3);
    pq.enqueue(104, "David", 8);

    pq.display();

    cout << "\nPerforming Dequeue Operations:\n";
    pq.dequeue();
    pq.dequeue();

    pq.display();

    return 0;
}
```
## Create a struct BookNode:

int id; string title; string author; bool issued;

BookNode* next

Create a class Library with:

BookNode* head

addBook(), issueBook(id), returnBook(id), searchBook(title), displayAll()

Use pointers to traverse linked list and manage memory safely.
```
#include <iostream>
#include <string>
using namespace std;

struct BookNode {
    int id;
    string title;
    string author;
    bool issued;
    BookNode* next;
};

class Library {
private:
    BookNode* head;

public:
    // Constructor
    Library() {
        head = nullptr;
    }

    // Destructor (free memory safely)
    ~Library() {
        BookNode* temp;
        while (head != nullptr) {
            temp = head;
            head = head->next;
            delete temp;
        }
    }

    // Add Book (insert at end)
    void addBook(int id, string title, string author) {
        BookNode* newBook = new BookNode;
        newBook->id = id;
        newBook->title = title;
```
## Create a struct Transaction:

string type; double amount; string date; Transaction* next

Create a class BankAccount:

private: accountNo, holderName, balance, Transaction* historyHead

deposit(), withdraw(), showHistory(), showBalance()

Store multiple accounts using BankAccount* array pointer and search account by number.
```
#include <iostream>
#include <string>
using namespace std;

struct Transaction {
    string type;      // Deposit / Withdraw
    double amount;
    string date;
    Transaction* next;
};

class BankAccount {
private:
    int accountNo;
    string holderName;
    double balance;
    Transaction* historyHead;

public:
    // Constructor
    BankAccount() {
        accountNo = 0;
        holderName = "";
        balance = 0.0;
        historyHead = nullptr;
    }

    BankAccount(int accNo, string name, double initialBalance) {
        accountNo = accNo;
        holderName = name;
        balance = initialBalance;
        historyHead = nullptr;
    }

    // Destructor (free transaction history memory)
    ~BankAccount() {
        Transaction* temp;
        while (historyHead != nullptr) {
            temp = historyHead;
            historyHead = historyHead->next;
            delete temp;
        }
    }

    int getAccountNo() const {
        return accountNo;
    }

    void deposit(double amount, string date) {
        balance += amount;

        Transaction* newTrans = new Transaction;
        newTrans->type = "Deposit";
        newTrans->amount = amount;
        newTrans->date = date;
        newTrans->next = historyHead;
        historyHead = newTrans;

        cout << "Deposit successful!\n";
    }

    void withdraw(double amount, string date) {
        if (amount > balance) {
            cout << "Insufficient balance!\n";
            return;
        }

        balance -= amount;

        Transaction* newTrans = new Transaction;
        newTrans->type = "Withdraw";
        newTrans->amount = amount;
        newTrans->date = date;
        newTrans->next = historyHead;
        historyHead = newTrans;

        cout << "Withdrawal successful!\n";
    }

    void showBalance() const {
        cout << "Account No: " << accountNo
             << "\nHolder Name: " << holderName
             << "\nBalance: " << balance << endl;
    }

    void showHistory() const {
        if (historyHead == nullptr) {
            cout << "No transactions found.\n";
            return;
        }

        Transaction* temp = historyHead;
        cout << "\n--- Transaction History ---\n";

        while (temp != nullptr) {
            cout << temp->date << " | "
                 << temp->type << " | "
                 << temp->amount << endl;
            temp = temp->next;
        }
    }
};

int main() {
    int n;

    cout << "Enter number of accounts: ";
    cin >> n;

    // Dynamic array of BankAccount objects
    BankAccount* accounts = new BankAccount[n];

    // Input account details
    for (int i = 0; i < n; i++) {
        int accNo;
        string name;
        double balance;

        cout << "\nEnter Account No: ";
        cin >> accNo;
        cout << "Enter Holder Name: ";
        cin >> name;
        cout << "Enter Initial Balance: ";
        cin >> balance;

        accounts[i] = BankAccount(accNo, name, balance);
    }

    // Search account by number
    int searchAcc;
    cout << "\nEnter account number to access: ";
    cin >> searchAcc;

    BankAccount* found = nullptr;

    for (int i = 0; i < n; i++) {
        if (accounts[i].getAccountNo() == searchAcc) {
            found = &accounts[i];
            break;
        }
    }

    if (found != nullptr) {
        found->showBalance();
        found->deposit(500, "18-02-2026");
        found->withdraw(200, "18-02-2026");
        found->showBalance();
        found->showHistory();
    } else {
        cout << "Account not found!\n";
    }

    // Free memory
    delete[] accounts;

    return 0;
}
```
## create a struct Course:

courseCode, courseName, credits

Create a class Student:

roll, name

Course* registeredCourses (dynamic)

registerCourses(), dropCourse(code), showCourses(), totalCredits()

Store multiple students using pointers and print list of students registered in a given course.
```
#include <iostream>
#include <string>
using namespace std;

struct Course {
    string courseCode;
    string courseName;
    int credits;
};

class Student {
private:
    int roll;
    string name;
    Course* registeredCourses;
    int courseCount;

public:
    // Constructor
    Student() {
        roll = 0;
        name = "";
        registeredCourses = nullptr;
        courseCount = 0;
    }

    Student(int r, string n, int maxCourses) {
        roll = r;
        name = n;
        courseCount = 0;
        registeredCourses = new Course[maxCourses];
    }

    // Destructor
    ~Student() {
        delete[] registeredCourses;
    }

    int getRoll() const { return roll; }
    string getName() const { return name; }
    int getCourseCount() const { return courseCount; }
    Course* getCourses() const { return registeredCourses; }

    // Register course
    void registerCourse(string code, string cname, int credits) {
        registeredCourses[courseCount].courseCode = code;
        registeredCourses[courseCount].courseName = cname;
        registeredCourses[courseCount].credits = credits;
        courseCount++;
        cout << "Course registered successfully!\n";
    }

    // Drop course by code
    void dropCourse(string code) {
        for (int i = 0; i < courseCount; i++) {
            if (registeredCourses[i].courseCode == code) {
                // Shift left
                for (int j = i; j < courseCount - 1; j++) {
                    registeredCourses[j] = registeredCourses[j + 1];
                }
                courseCount--;
                cout << "Course dropped successfully!\n";
                return;
            }
        }
        cout << "Course not found!\n";
    }

    // Show registered courses
    void showCourses() const {
        if (courseCount == 0) {
            cout << "No courses registered.\n";
            return;
        }

        cout << "\nCourses for " << name << ":\n";
        for (int i = 0; i < courseCount; i++) {
            cout << registeredCourses[i].courseCode << " - "
                 << registeredCourses[i].courseName
                 << " (" << registeredCourses[i].credits << " credits)\n";
        }
    }

    // Total credits
    int totalCredits() const {
        int total = 0;
        for (int i = 0; i < courseCount; i++) {
            total += registeredCourses[i].credits;
        }
        return total;
    }
};

int main() {
    int n, maxCourses;

    cout << "Enter number of students: ";
    cin >> n;

    cout << "Enter max courses per student: ";
    cin >> maxCourses;

    Student* students = new Student[n];

    // Input student details
    for (int i = 0; i < n; i++) {
        int roll;
        string name;

        cout << "\nEnter Roll No: ";
        cin >> roll;
        cout << "Enter Name: ";
        cin >> name;

        students[i] = Student(roll, name, maxCourses);

        int c;
        cout << "How many courses to register? ";
        cin >> c;

        for (int j = 0; j < c; j++) {
            string code, cname;
            int credits;

            cout << "Course Code: ";
            cin >> code;
            cout << "Course Name: ";
            cin >> cname;
            cout << "Credits: ";
            cin >> credits;

            students[i].registerCourse(code, cname, credits);
        }
    }

    // Display all students and courses
    cout << "\n--- Student Course Details ---\n";
    for (int i = 0; i < n; i++) {
        cout << "\nRoll: " << students[i].getRoll()
             << ", Name: " << students[i].getName() << endl;
        students[i].showCourses();
        cout << "Total Credits: " << students[i].totalCredits() << endl;
    }

    // Print students registered in a given course
    string searchCode;
    cout << "\nEnter course code to search students: ";
    cin >> searchCode;

    cout << "\nStudents registered in " << searchCode << ":\n";

    for (int i = 0; i < n; i++) {
        Course* courses = students[i].getCourses();
        for (int j = 0; j < students[i].getCourseCount(); j++) {
            if (courses[j].courseCode == searchCode) {
                cout << students[i].getRoll()
                     << " - " << students[i].getName() << endl;
            }
        }
    }

    // Free memory
    delete[] students;

    return 0;
}
```
## Create a struct DirNode:

string name; bool isFile;

DirNode* child; DirNode* sibling;

Create a class DirectoryTree:

createFolder(path), createFile(path)

list(path)

deleteNode(path)
Implement using pointers (tree navigation) and free memory in destructor.
```
#include <iostream>
#include <string>
#include <sstream>
using namespace std;

struct DirNode {
    string name;
    bool isFile;
    DirNode* child;     // first child
    DirNode* sibling;   // next sibling
};

class DirectoryTree {
private:
    DirNode* root;

    // Utility: split path by '/'
    string getNextToken(stringstream &ss) {
        string token;
        getline(ss, token, '/');
        return token;
    }

    // Find node by path
    DirNode* findNode(string path) {
        if (path == "/") return root;

        stringstream ss(path);
        string token;
        DirNode* current = root;

        while (getline(ss, token, '/')) {
            if (token.empty()) continue;

            DirNode* child = current->child;
            while (child != nullptr && child->name != token) {
                child = child->sibling;
            }

            if (child == nullptr)
                return nullptr;

            current = child;
        }
        return current;
    }

    // Recursive delete subtree
    void deleteSubtree(DirNode* node) {
        if (!node) return;

        deleteSubtree(node->child);
        deleteSubtree(node->sibling);
        delete node;
    }

public:
    DirectoryTree() {
        root = new DirNode{"/", false, nullptr, nullptr};
    }

    ~DirectoryTree() {
        deleteSubtree(root);
    }

    // Create folder
    void createFolder(string path) {
        int pos = path.find_last_of('/');
        string parentPath = path.substr(0, pos);
        string folderName = path.substr(pos + 1);

        if (parentPath.empty()) parentPath = "/";

        DirNode* parent = findNode(parentPath);
        if (!parent || parent->isFile) {
            cout << "Invalid parent path!\n";
            return;
        }

        DirNode* newNode = new DirNode{folderName, false, nullptr, nullptr};

        // Insert as first child
        newNode->sibling = parent->child;
        parent->child = newNode;

        cout << "Folder created successfully!\n";
    }

    // Create file
    void createFile(string path) {
        int pos = path.find_last_of('/');
        string parentPath = path.substr(0, pos);
        string fileName = path.substr(pos + 1);

        if (parentPath.empty()) parentPath = "/";

        DirNode* parent = findNode(parentPath);
        if (!parent || parent->isFile) {
            cout << "Invalid parent path!\n";
            return;
        }

        DirNode* newNode = new DirNode{fileName, true, nullptr, nullptr};

        newNode->sibling = parent->child;
        parent->child = newNode;

        cout << "File created successfully!\n";
    }

    // List contents
    void list(string path) {
        DirNode* node = findNode(path);

        if (!node) {
            cout << "Path not found!\n";
            return;
        }

        DirNode* child = node->child;
        cout << "\nContents of " << path << ":\n";

        while (child != nullptr) {
            cout << (child->isFile ? "[File] " : "[Folder] ")
                 << child->name << endl;
            child = child->sibling;
        }
    }

    // Delete node by path
    void deleteNode(string path) {
        if (path == "/") {
            cout << "Cannot delete root!\n";
            return;
        }

        int pos = path.find_last_of('/');
        string parentPath = path.substr(0, pos);
        string nodeName = path.substr(pos + 1);

        if (parentPath.empty()) parentPath = "/";

        DirNode* parent = findNode(parentPath);
        if (!parent) {
            cout << "Parent path not found!\n";
            return;
        }

        DirNode* current = parent->child;
        DirNode* prev = nullptr;

        while (current && current->name != nodeName) {
            prev = current;
            current = current->sibling;
        }

        if (!current) {
            cout << "Node not found!\n";
            return;
        }

        // Remove from sibling chain
        if (prev)
            prev->sibling = current->sibling;
        else
            parent->child = current->sibling;

        current->sibling = nullptr;
        deleteSubtree(current);

        cout <
```

}
```

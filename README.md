# C++ Integer Pointers and Memory Management

A C++ console application developed for **CSC450 — Programming III** at Colorado State University Global.

This project demonstrates integer pointers, dynamic memory allocation, pointer dereferencing, and manual memory management using the `new` and `delete` operators.

## Project Overview

The application prompts the user to enter three integer values. Each value is initially stored in a regular integer variable and then copied into a separate dynamically allocated memory location using an integer pointer.

The program displays:

- The three original integer values
- The memory address held by each pointer
- The integer value stored at each dynamically allocated location

After displaying the information, the program releases the allocated memory and sets each pointer to `nullptr`.

The assignment introduces fundamental concepts of C++ memory management and the relationship between variables, pointers, and dynamically allocated memory.

## Technologies Used

- **C++** — Programming language
- **C++ Standard Library** — Console input and output
- **Visual Studio Code** — Development environment
- **MSYS2 / MinGW-w64** — C++ compiler toolchain
- **Git and GitHub** — Version control and documentation

## Project Structure

```text
cpp-integer-pointers-and-memory-management/
├── CSC450_CT3_IntegerPointers.cpp
├── .gitignore
├── LICENSE
└── README.md
```

## How the Program Works

The application follows these steps:

1. Declare three integer variables.
2. Prompt the user to enter three integer values.
3. Allocate three separate memory locations using `new`.
4. Copy each entered integer into its corresponding allocated location.
5. Display the original integer values.
6. Display the memory addresses stored in the pointers.
7. Dereference the pointers to display the stored values.
8. Release the dynamically allocated memory using `delete`.
9. Set each pointer to `nullptr`.
10. Exit the program successfully.

## Key Programming Concepts

### Integer Variables

The program begins by declaring three integer variables:

```cpp
int firstValue;
int secondValue;
int thirdValue;
```

These variables store the values entered by the user.

### Integer Pointers

A pointer is a variable that stores a memory address.

The program declares three integer pointers and dynamically allocates memory for each:

```cpp
int *firstPointer = new int;
int *secondPointer = new int;
int *thirdPointer = new int;
```

Each pointer stores the address of a separately allocated integer.

### Dynamic Memory Allocation

The `new` operator allocates memory during program execution.

Unlike ordinary local variables, memory allocated with `new` must be explicitly released when it is no longer needed.

The program allocates memory for three integers independently.

### Pointer Dereferencing

The dereference operator (`*`) allows the program to access or modify the value stored at the memory address held by a pointer.

```cpp
*firstPointer = firstValue;
*secondPointer = secondValue;
*thirdPointer = thirdValue;
```

These statements copy the user-entered integer values into dynamically allocated memory.

The program later displays those values:

```cpp
cout << "First pointer value: " << *firstPointer << endl;
cout << "Second pointer value: " << *secondPointer << endl;
cout << "Third pointer value: " << *thirdPointer << endl;
```

### Memory Addresses

The program displays the addresses stored in the three pointers:

```cpp
cout << "First pointer: " << firstPointer << endl;
cout << "Second pointer: " << secondPointer << endl;
cout << "Third pointer: " << thirdPointer << endl;
```

These statements display pointer addresses rather than the integer values stored at those addresses.

Memory addresses vary between executions and systems.

### Memory Deallocation

After the program finishes using the allocated memory, it releases each allocation:

```cpp
delete firstPointer;
delete secondPointer;
delete thirdPointer;
```

The `delete` operator releases memory previously allocated with `new`.

Failing to release dynamically allocated memory can cause memory leaks.

### Null Pointers

After deallocating memory, the program resets each pointer:

```cpp
firstPointer = nullptr;
secondPointer = nullptr;
thirdPointer = nullptr;
```

Setting a pointer to `nullptr` prevents it from continuing to hold an address to memory that has already been released.

This is a useful defensive programming practice when working with raw pointers.

## Pseudocode

The original C++ source file includes pseudocode outlining the program's logic.

```text
START

DECLARE firstValue, secondValue, and thirdValue as integers
DECLARE firstPointer, secondPointer, and thirdPointer as integer pointers

PROMPT user for first integer
READ firstValue

PROMPT user for second integer
READ secondValue

PROMPT user for third integer
READ thirdValue

ALLOCATE dynamic memory for firstPointer
ALLOCATE dynamic memory for secondPointer
ALLOCATE dynamic memory for thirdPointer

STORE firstValue at firstPointer location
STORE secondValue at secondPointer location
STORE thirdValue at thirdPointer location

PRINT original integer values
PRINT pointer addresses
PRINT values stored at pointer locations

DELETE dynamic memory used by firstPointer
DELETE dynamic memory used by secondPointer
DELETE dynamic memory used by thirdPointer

SET firstPointer to nullptr
SET secondPointer to nullptr
SET thirdPointer to nullptr

END
```

This pseudocode demonstrates the program's intended sequence before implementation.

## How to Compile and Run

### Requirements

- A C++ compiler such as g++ through MSYS2 / MinGW-w64
- A terminal or command prompt
- Windows, Linux, or macOS with a compatible C++ development environment

### Step 1 — Clone the Repository

```bash
git clone https://github.com/Tentei06/cpp-integer-pointers-and-memory-management.git
```

Navigate to the project directory:

```bash
cd cpp-integer-pointers-and-memory-management
```

### Step 2 — Compile the Program

```bash
g++ CSC450_CT3_IntegerPointers.cpp -o integer-pointers
```

### Step 3 — Run the Program

**Windows (PowerShell):**

```powershell
.\integer-pointers.exe
```

**Linux or macOS:**

```bash
./integer-pointers
```

Enter three integers when prompted.

## Example Execution

The following example demonstrates the expected program behavior.

```text
Enter the first integer: 10
Enter the second integer: 25
Enter the third integer: 50

Integer Values:
First value: 10
Second value: 25
Third value: 50

Pointer Addresses:
First pointer: 0x123456
Second pointer: 0x123478
Third pointer: 0x123490

Values Stored in Dynamic Memory:
First pointer value: 10
Second pointer value: 25
Third pointer value: 50
```

**Note:** The memory addresses shown above are illustrative placeholders. Actual addresses will vary between program executions.

## Testing and Verification

The original assignment involved compiling and executing the application to verify its behavior.

The following scenarios describe the program's expected functionality.

| Test Scenario | Expected Result |
|---------------|-----------------|
| Enter three positive integers | All values display correctly |
| Enter zero | Zero is stored and displayed correctly |
| Enter negative integers | Negative values are stored and displayed correctly |
| Display pointer addresses | Each pointer displays a memory address |
| Dereference pointers | Stored values match the entered integers |
| Release allocated memory | Each allocation is released using `delete` |
| Reset pointers | Each pointer is assigned `nullptr` before program termination |

The program demonstrates basic pointer operations and manual memory management.

## Development Process

The original assignment involved:

1. Reviewing the requirements for using integer pointers.
2. Developing pseudocode to outline the program.
3. Declaring variables to store three user-entered integers.
4. Allocating memory dynamically using `new`.
5. Copying integer values into the allocated memory.
6. Displaying the original values and pointer addresses.
7. Using pointer dereferencing to access stored values.
8. Releasing memory with `delete`.
9. Resetting pointers to `nullptr`.
10. Compiling and testing the completed application.

The source code retains the original coursework structure and explanatory comments.

## Limitations

This application is an introductory programming exercise rather than a production-ready memory management system.

- The program accepts exactly three integer values.
- It does not validate non-integer input.
- It uses raw pointers rather than modern C++ smart pointers.
- It does not save information to a file or database.
- The application executes once and then terminates.
- It does not include a graphical user interface.

The use of raw pointers is intentional because the assignment focuses on understanding manual memory allocation and deallocation.

For larger modern C++ applications, standard containers and smart pointers are generally preferred when appropriate.

## Educational Context

This project was developed for the **Module 3 Critical Thinking assignment** in CSC450 — Programming III at Colorado State University Global.

It demonstrates foundational skills in:

- Integer variables and console input
- Pointer declarations
- Dynamic memory allocation
- Pointer dereferencing
- Memory address inspection
- Manual memory deallocation
- Null pointer assignment
- Pseudocode and program planning

These concepts provide a foundation for understanding memory management, data structures, and resource ownership in more advanced C++ applications.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

# EX-26-AREA-OF-RECTANGLE-USING- POINTER

## AIM

To write a C Program to find area of rectangle using pointer.

## ALGORITHM

1. Start the program.
2. Declare variables length, breadth, and area.
3. Declare pointers p1 and p2.
4. Read values of length and breadth from the user.
5. Assign addresses:
   p1 = &length
   p2 = &breadth
6. Calculate area using pointers:
   area = (*p1) * (*p2)
7. Display the area.
8. Stop the program.
9. 
## PROGRAM

```
#include <stdio.h>

int main() {
    int length, breadth, area;
    int *p1, *p2;

    printf("Enter length and breadth: ");
    scanf("%d %d", &length, &breadth);

    p1 = &length;
    p2 = &breadth;

    area = (*p1) * (*p2);

    printf("Area of rectangle = %d", area);

    return 0;
}

```

## OUTPUT
```
Enter length and breadth: 10 5
Area of rectangle = 50
```
## RESULT

Thus the program to find area of rectangle using pointer has been executed successfully

# EX-27-DYNAMIC-MEMORY-ALLOCATION

## AIM

To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM

1. Start the program.
2. Declare a character pointer.
3. Allocate memory using malloc() for storing the string "WELCOME".
4. Store the string in the allocated memory.
5. Print the string.
6. Free the allocated memory using free().
7. Stop the program.
   
## PROGRAM

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char *ptr;

    // Allocate memory for 8 characters (WELCOME + '\0')
    ptr = (char *)malloc(8 * sizeof(char));

    if (ptr == NULL) {
        printf("Memory allocation failed");
        return 1;
    }

    // Copy string into allocated memory
    strcpy(ptr, "WELCOME");

    // Print the string
    printf("%s", ptr);

    // Free allocated memory
    free(ptr);

    return 0;
}

```

## OUTPUT
```
WELCOME
```
## RESULT

Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully.

# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1. Start the program.
2. Define a structure student with fields: roll, name, and marks.
3. Declare a structure variable.
4. Read student details from the user.
5. Display the stored student information.
6. Stop the program.m.

## PROGRAM

```
#include <stdio.h>

struct student {
    int roll;
    char name[50];
    float marks;
};

int main() {
    struct student s;

    printf("Enter Roll Number: ");
    scanf("%d", &s.roll);

    printf("Enter Name: ");
    scanf("%s", s.name);

    printf("Enter Marks: ");
    scanf("%f", &s.marks);

    printf("\nStudent Details:\n");
    printf("Roll Number: %d\n", s.roll);
    printf("Name: %s\n", s.name);
    printf("Marks: %.2f\n", s.marks);

    return 0;
}

```

## OUTPUT
```
Enter Roll Number: 101
Enter Name: Ravi
Enter Marks: 85.5

Student Details:
Roll Number: 101
Name: Ravi
Marks: 85.50
```
## RESULT

Thus the program to store the student information and display it using structure has been executed successfully.

# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1. Start the program.
2. Define a structure employee with fields:
   id, name, basic, hra, da, gross.
3. Declare an array of 3 employees.
4. For each employee (loop 3 times):
5. Read id, name, and basic salary.
6. Calculate:
   hra = 20% of basic
   da = 10% of basic
   gross = basic + hra + da
7. Display details of all employees including gross salary.
8. Stop the program.
   
## PROGRAM

```
#include <stdio.h>

struct employee {
    int id;
    char name[50];
    float basic, hra, da, gross;
};

int main() {
    struct employee e[3];
    int i;

    // Input
    for (i = 0; i < 3; i++) {
        printf("\nEnter details of employee %d\n", i + 1);

        printf("Enter ID: ");
        scanf("%d", &e[i].id);

        printf("Enter Name: ");
        scanf("%s", e[i].name);

        printf("Enter Basic Salary: ");
        scanf("%f", &e[i].basic);

        // Calculations
        e[i].hra = 0.20 * e[i].basic;
        e[i].da = 0.10 * e[i].basic;
        e[i].gross = e[i].basic + e[i].hra + e[i].da;
    }

    // Output
    printf("\nEmployee Details:\n");
    for (i = 0; i < 3; i++) {
        printf("\nID: %d\n", e[i].id);
        printf("Name: %s\n", e[i].name);
        printf("Basic Salary: %.2f\n", e[i].basic);
        printf("Gross Salary: %.2f\n", e[i].gross);
    }

    return 0;
}

```

## OUTPUT
```
Enter details of employee 1
Enter ID: 101
Enter Name: Ravi
Enter Basic Salary: 10000

Enter details of employee 2
Enter ID: 102
Enter Name: Kumar
Enter Basic Salary: 12000

Enter details of employee 3
Enter ID: 103
Enter Name: Anu
Enter Basic Salary: 15000

Employee Details:

ID: 101
Name: Ravi
Basic Salary: 10000.00
Gross Salary: 13000.00

ID: 102
Name: Kumar
Basic Salary: 12000.00
Gross Salary: 15600.00

ID: 103
Name: Anu
Basic Salary: 15000.00
Gross Salary: 19500.00
```
## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM

Create a C program to calculate the total and average of student using structure.

## ALGORITHM

1. Start the program.
2. Define a structure student with fields:
   name, marks1, marks2, marks3, total, average.
3. Declare a structure variable.
4. Read student name and marks of 3 subjects.
5. Calculate:
   total = marks1 + marks2 + marks3
   average = total / 3.0
6. Display student details, total, and average.
7. Stop the program.


## PROGRAM

```
#include <stdio.h>

struct student {
    char name[50];
    int marks1, marks2, marks3;
    int total;
    float average;
};

int main() {
    struct student s;

    printf("Enter student name: ");
    scanf("%s", s.name);

    printf("Enter marks of 3 subjects: ");
    scanf("%d %d %d", &s.marks1, &s.marks2, &s.marks3);

    // Calculate total and average
    s.total = s.marks1 + s.marks2 + s.marks3;
    s.average = s.total / 3.0;

    // Display
    printf("\nStudent Details:\n");
    printf("Name: %s\n", s.name);
    printf("Total Marks: %d\n", s.total);
    printf("Average: %.2f\n", s.average);

    return 0;
}

```

## OUTPUT
```
Enter student name: Ravi
Enter marks of 3 subjects: 80 75 85

Student Details:
Name: Ravi
Total Marks: 240
Average: 80.00
```
## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.

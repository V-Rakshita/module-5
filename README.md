# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM

```c
#include <stdio.h>
int main()
{
    float x, y;
    float *px = &x;
    float *py = &y;
    float area;
    printf("Enter length: ");
    scanf("%f", px);
    printf("Enter breadth: ");
    scanf("%f", py);
    area = (*px) * (*py);
    printf("Area of rectangle = %.2f\n", area);
    return 0;
}
```

## OUTPUT
		       	
![image](https://github.com/user-attachments/assets/42206111-a763-4720-aafa-6843ed224401)



## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int main()
{
    char *ptr = malloc(8 * sizeof(char));
    if (ptr==NULL)
    {
        printf("Memory allocation failed");
        return 1;
    }
    strcpy(ptr,"WELCOME");
    printf("%s",ptr);
    free(ptr);
}
```
## OUTPUT

![image](https://github.com/user-attachments/assets/5049aa8a-bfe1-4351-9690-5028492ad75d)


## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
struct student
{
    char name[20];
    int rollno;
    int marks;
};

void display(struct student s)
{
    printf("Name is: %s\n",s.name);
    printf("Rollno is: %d\n",s.rollno);
    printf("Marks is: %d\n",s.marks);
}

int main()
{
    struct student s1;
    scanf("%s",s1.name);
    scanf("%d",&s1.rollno);
    scanf("%d",&s1.marks);
    display(s1);
}
```
## OUTPUT

![image](https://github.com/user-attachments/assets/a89496bd-2369-48ec-8357-df556362bbed)

## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM

```c
#include <stdio.h>
struct employee
{
    int empno;
    char dept[10];
    int basicpay;
    float da;
    float hra;
    float gross;
}e[3];

int main()
{
    int i;
    for (i=0;i<3;i++)
    {
        scanf("%d%s%d",&e[i].empno,e[i].dept,&e[i].basicpay);
        e[i].da = (0.1 * e[i].basicpay);
        e[i].hra = (0.3 * e[i].basicpay);
        e[i].gross = e[i].da+e[i].hra+e[i].basicpay;
    }
    printf("Details of the Employee:\n");
    
    for (i=0;i<3;i++)
    {
        printf("%d %s %d %.f %.f %.2f \n",e[i].empno,e[i].dept,e[i].basicpay,e[i].da,e[i].hra,e[i].gross);
    }
}
```

 ## OUTPUT

 ![image](https://github.com/user-attachments/assets/bf564129-0671-4bd8-93fc-1808bd2cd104)


## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```c
#include <stdio.h>
struct student {
    char name[10];
    int rollno;
    int subject[5];
    int total;
};
int main() {
    struct student s[2];
    int i, j;
    for (i = 0; i < 2; i++) {
        printf("Enter roll number for student %d: ", i + 1);
        scanf("%d", &s[i].rollno);
        printf("Enter marks for 5 subjects of student %d:\n", i + 1);
        for (j = 0; j < 5; j++) {
            scanf("%d", &s[i].subject[j]);
        }
    }
    for (i = 0; i < 2; i++) {
        s[i].total = 0;
        for (j = 0; j < 5; j++) {
            s[i].total += s[i].subject[j];
        }
    }
    for (i = 0; i < 2; i++) {
        printf("Total marks of student %d: %d\n", i + 1, s[i].total);
    }
}

```
## OUTPUT

 ![image](https://github.com/user-attachments/assets/04617b84-b71d-4ed2-96d6-a6a09e4bea59)


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	



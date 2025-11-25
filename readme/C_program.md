📘 C Programming Course (Beginner to Advanced)

Learn C programming for college exams, interviews, system programming, OS-level development, embedded systems, and logic building.

⭐ 1. Introduction to C
What is C?

C is a powerful, low-level programming language.

Used for:

Operating systems (Linux is written in C)

Compilers

Embedded systems, microcontrollers

Game engines

System-level programming

⭐ 2. Install & Setup
🖥 Windows

Install MinGW or TDM-GCC
Check:

gcc --version

🧑‍💻 Compile & Run C Program
gcc program.c -o program
./program

⭐ 3. Basic Structure of a C Program
#include <stdio.h>

int main() {
    printf("Hello World!");
    return 0;
}

⭐ 4. Variables and Data Types
int age = 20;
float height = 5.8;
char grade = 'A';
double salary = 50000.50;

Data Types Table
Type	Description
int	Whole numbers
float	Decimal (6 digits precision)
double	Decimal (15 digits precision)
char	Single character
void	No value
⭐ 5. Input & Output
Output
printf("Welcome!");

Input
int age;
scanf("%d", &age);

Symbol	Meaning
%d	int
%f	float
%c	char
%s	string
⭐ 6. Operators
Arithmetic
+, -, *, /, %

Comparison
==, !=, >, <, >=, <=

Logical
&&, ||, !

⭐ 7. Conditional Statements
If / Else
int marks = 80;

if(marks >= 50) {
    printf("Pass");
} else {
    printf("Fail");
}

Switch
switch(day) {
    case 1: printf("Monday"); break;
    case 2: printf("Tuesday"); break;
    default: printf("Other day");
}

⭐ 8. Loops
For Loop
for(int i = 1; i <= 5; i++) {
    printf("%d ", i);
}

While Loop
int i = 1;
while(i <= 5) {
    printf("%d ", i);
    i++;
}

Do While Loop
int i = 1;
do {
    printf("%d ", i);
    i++;
} while(i <= 5);

⭐ 9. Arrays
int nums[3] = {10, 20, 30};
printf("%d", nums[1]);


Multidimensional:

int matrix[2][2] = {
  {1, 2},
  {3, 4}
};

⭐ 10. Strings
char name[20] = "Jusair";
printf("%s", name);

⭐ 11. Functions
Function with parameters
void greet(char name[]) {
    printf("Hello %s", name);
}

int main() {
    greet("Ali");
}

Return values
int add(int a, int b) {
    return a + b;
}

⭐ 12. Pointers
int x = 10;
int *p = &x;

printf("%d", *p); // 10

⭐ 13. Pointer + Array Relationship
int arr[3] = {10, 20, 30};
int *p = arr;

printf("%d", *(p+1)); // 20

⭐ 14. Structures (struct)
struct Student {
    char name[20];
    int age;
};

struct Student s1 = {"Ali", 20};
printf("%s %d", s1.name, s1.age);

⭐ 15. File Handling
Write file
FILE *f = fopen("data.txt", "w");
fprintf(f, "Hello!");
fclose(f);

Read file
FILE *f = fopen("data.txt", "r");
char text[100];
fgets(text, 100, f);
printf("%s", text);
fclose(f);

⭐ 16. Dynamic Memory Allocation
int *p = malloc(4 * sizeof(int));
*p = 20;
printf("%d", *p);
free(p);

⭐ 17. Recursion
int fact(int n) {
    if(n == 1) return 1;
    return n * fact(n - 1);
}

⭐ 18. C Programs (Mini Projects)
➤ 1. Calculator
int a,b;
char op;

scanf("%d %c %d", &a, &op, &b);

switch(op) {
  case '+': printf("%d", a+b); break;
  case '-': printf("%d", a-b); break;
  case '*': printf("%d", a*b); break;
  case '/': printf("%d", a/b); break;
}

➤ 2. Guessing Game
int num = 7, guess;

while(guess != num) {
    printf("Guess: ");
    scanf("%d", &guess);
}
printf("Correct!");

➤ 3. Student Marksheet
int m1, m2, m3;
scanf("%d %d %d", &m1, &m2, &m3);

int total = m1+m2+m3;
float avg = total/3.0;

printf("Total = %d\n", total);
printf("Average = %.2f", avg);

⭐ 19. Interview Topics (Important)

Storage classes

Call by value vs reference

Dangling pointers

malloc vs calloc

Stack vs Heap

Time complexity basics

Bitwise operators

⭐ 20. What Next? (Advanced C)

✔ Data structures in C
✔ Linked list
✔ Stack
✔ Queue
✔ Tree
✔ Graph
✔ Sorting algorithms
✔ System programming
✔ Embedded C
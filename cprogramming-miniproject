#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_STUDENTS 100

// Structure to store student data
typedef struct {
    int id;
    char name[50];
    char grade;
    float marks;
} Student;

Student students[MAX_STUDENTS];
int student_count = 0;

// Function to add a student record
void addStudent() {
    if (student_count >= MAX_STUDENTS) {
        printf("Error: Maximum student limit reached.\n");
        return;
    }
    Student s;
    printf("Enter Student ID: ");
    scanf("%d", &s.id);
    printf("Enter Student Name: ");
    scanf(" %[^\n]", s.name);
    printf("Enter Student Grade: ");
    scanf(" %c", &s.grade);
    printf("Enter Student Marks: ");
    scanf("%f", &s.marks);
    
    students[student_count++] = s;
    printf("Student added successfully!\n");
}

// Function to search for a student by ID or Name
void searchStudent() {
    int choice;
    printf("Search by: 1. ID 2. Name\n");
    printf("Enter your choice: ");
    scanf("%d", &choice);
    
    if (choice == 1) {
        int id;
        printf("Enter Student ID: ");
        scanf("%d", &id);
        for (int i = 0; i < student_count; i++) {
            if (students[i].id == id) {
                printf("\nID: %d, Name: %s, Grade: %c, Marks: %.2f\n", 
                        students[i].id, students[i].name, students[i].grade, students[i].marks);
                return;
            }
        }
    } else if (choice == 2) {
        char name[50];
        printf("Enter Student Name: ");
        scanf(" %[^\n]", name);
        for (int i = 0; i < student_count; i++) {
            if (strcmp(students[i].name, name) == 0) {
                printf("\nID: %d, Name: %s, Grade: %c, Marks: %.2f\n", 
                        students[i].id, students[i].name, students[i].grade, students[i].marks);
                return;
            }
        }
    } else {
        printf("Invalid choice.\n");
        return;
    }
    printf("Student not found.\n");
}

// Function to display all student records
void displayStudents() {
    if (student_count == 0) {
        printf("No student records available.\n");
        return;
    }
    printf("\nStudent Records:\n");
    for (int i = 0; i < student_count; i++) {
        printf("ID: %d, Name: %s, Grade: %c, Marks: %.2f\n", 
                students[i].id, students[i].name, students[i].grade, students[i].marks);
    }
}

// Function to calculate the average marks of the class
void calculateAverage() {
    if (student_count == 0) {
        printf("No student records to calculate average.\n");
        return;
    }
    float total = 0;
    for (int i = 0; i < student_count; i++) {
        total += students[i].marks;
    }
    printf("Average Marks: %.2f\n", total / student_count);
}

int main() {
    int choice;
    while (1) {
        printf("\nStudent Record Management System\n");
        printf("1. Add Student\n");
        printf("2. Search Student\n");
        printf("3. Display All Students\n");
        printf("4. Calculate Average Marks\n");
        printf("5. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                addStudent();
                break;
            case 2:
            searchStudent();
                break;
            case 3:
                displayStudents();
                break;
            case 4:
                calculateAverage();
                break;
            case 5:
                printf("Exiting program.\n");
                exit(0);
            default:
                printf("Invalid choice. Please try again.\n");
        }
}
return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_STUDENTS 100

typedef struct Student {
    int student_id;
    char name[100];
    float grade;
} Student;

void add_student(Student students[], int *count);
void search_student(Student students[], int count, int student_id);
void display_students(Student students[], int count);
void display_grade(Student students[], int count, int student_id);

int main() {
    Student students[MAX_STUDENTS];
    int count = 0;
    int choice, student_id;

    while (1) {
        printf("\nStudent Grade Checker\n");
        printf("1. Add Student\n");
        printf("2. Display All Students\n");
        printf("3. Search for Student Grade\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                add_student(students, &count);
                break;

            case 2:
                display_students(students, count);
                break;

            case 3:
                printf("Enter Student ID to search: ");
                scanf("%d", &student_id);
                display_grade(students, count, student_id);
                break;

            case 4:
                printf("Exiting...\n");
                exit(0);

            default:
                printf("Invalid choice! Try again.\n");
        }
    }
    return 0;
}

void add_student(Student students[], int *count) {
    if (*count >= MAX_STUDENTS) {
        printf("Cannot add more students. Array is full.\n");
        return;
    }

    Student new_student;
    printf("Enter Student ID: ");
    scanf("%d", &new_student.student_id);
    printf("Enter Student Name: ");
    getchar();
    fgets(new_student.name, sizeof(new_student.name), stdin);
    new_student.name[strcspn(new_student.name, "\n")] = '\0';
    printf("Enter Student Grade (0-100): ");
    scanf("%f", &new_student.grade);

    students[*count] = new_student;
    (*count)++;
    printf("Student added successfully!\n");
}

void display_students(Student students[], int count) {
    if (count == 0) {
        printf("No students to display.\n");
        return;
    }
    printf("\nDisplaying All Students:\n");
    for (int i = 0; i < count; i++) {
        printf("ID: %d, Name: %s, Grade: %.2f\n", students[i].student_id, students[i].name, students[i].grade);
    }
}

void display_grade(Student students[], int count, int student_id) {
    for (int i = 0; i < count; i++) {
        if (students[i].student_id == student_id) {
            printf("Student Found: ID=%d, Name=%s, Grade=%.2f\n",
                   students[i].student_id, students[i].name, students[i].grade);
            return;
        }
    }
    printf("Student with ID %d not found!\n", student_id);
}

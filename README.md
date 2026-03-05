# student_management.py

class Student:
    def __init__(self, name, roll, course, marks):
        self.name = name
        self.roll = roll
        self.course = course
        self.marks = marks

    def display(self):
        print(f"Name: {self.name}")
        print(f"Roll No: {self.roll}")
        print(f"Course: {self.course}")
        print(f"Marks: {self.marks}")

class StudentManagement:
    def __init__(self):
        self.students = []

    def add_student(self):
        name = input("Enter student name: ")
        roll = input("Enter roll number: ")
        course = input("Enter course: ")
        marks = input("Enter marks: ")
        student = Student(name, roll, course, marks)
        self.students.append(student)
        print("Student added successfully!\n")

    def view_students(self):
        if not self.students:
            print("No students in the system.\n")
            return
        print("\n--- Student List ---")
        for student in self.students:
            student.display()
            print("------------------")
        print()

    def search_student(self):
        roll = input("Enter roll number to search: ")
        for student in self.students:
            if student.roll == roll:
                print("Student found:")
                student.display()
                print()
                return
        print("Student not found.\n")

    def delete_student(self):
        roll = input("Enter roll number to delete: ")
        for student in self.students:
            if student.roll == roll:
                self.students.remove(student)
                print("Student deleted successfully!\n")
                return
        print("Student not found.\n")

def main():
    sm = StudentManagement()
    while True:
        print("----- Student Management System -----")
        print("1. Add Student")
        print("2. View Students")
        print("3. Search Student")
        print("4. Delete Student")
        print("5. Exit")
        choice = input("Enter your choice: ")
        if choice == "1":
            sm.add_student()
        elif choice == "2":
            sm.view_students()
        elif choice == "3":
            sm.search_student()
        elif choice == "4":
            sm.delete_student()
        elif choice == "5":
            print("Exiting the program. Goodbye!")
            break
        else:
            print("Invalid choice. Try again.\n")

if __name__ == "__main__":
    main()

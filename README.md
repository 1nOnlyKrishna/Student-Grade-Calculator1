# Student-Grade-Calculator1
Student grade calculator 
class Student:
    def __init__(self, name):
        self.name = name
        self.marks = []

    def input_marks(self):
        num = int(input("Enter number of subjects: "))

        for i in range(1, num + 1):
            mark = float(input(f"Enter marks for subject {i}: "))
            self.marks.append(mark)

    def calculate_percentage(self):
        total = sum(self.marks)
        percentage = total / len(self.marks)
        return total, percentage

    def calculate_grade(self, percentage):
        if percentage > 90:
            return "A"
        elif 75 <= percentage <= 89:
            return "B"
        elif 60 <= percentage <= 74:
            return "C"
        elif 40 <= percentage <= 59:
            return "D"
        else:
            return "Fail"

    def display_result(self):
        total, percentage = self.calculate_percentage()
        grade = self.calculate_grade(percentage)

        print("\n----- Student Report Card -----")
        print(f"Student Name: {self.name}")
        print("Subject Marks:", self.marks)
        print(f"Total Marks: {total}")
        print(f"Percentage: {percentage:.2f}%")
        print(f"Final Grade: {grade}")


# ------- Main Program -------
name = input("Enter student name: ")
student = Student(name)

student.input_marks()
student.display_result()

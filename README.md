class GradeBookManager:
    def __init__(self):
        self.grade_book = {}

    def upload_grades(self, teacher_name, grades):
        if teacher_name not in self.grade_book:
            self.grade_book[teacher_name] = grades
        else:
            self.grade_book[teacher_name].extend(grades)

    def print_grade_book(self):
        for teacher, grades in self.grade_book.items():
            print(f"Teacher: {teacher}")
            for student, grade in grades.items():
                print(f"Student: {student}, Grade: {grade}")

# Example usage:
grade_manager = GradeBookManager()

# Teacher 1 uploads grades
teacher1_name = "Mr. Nauman"
teacher1_grades = {"Ali": 90, "hassan": 85, "adnan": 95}
grade_manager.upload_grades(teacher1_name, teacher1_grades)

# Teacher 2 uploads grades
teacher2_name = "Mrs. shahid"
teacher2_grades = {"Ali": 92, "Hassan": 87, "Adnan": 96}
grade_manager.upload_grades(teacher2_name, teacher2_grades)

# Print the grade book
grade_manager.print_grade_book()

# ER Diagram Submission - SANDHIYA R (212223240146)

## Scenario Chosen:
University 

## ER Diagram:
![image](https://github.com/user-attachments/assets/3084bcc6-872a-4a09-8325-cdf14d78ef07)


## Entities and Attributes:
Student: Name, DOB, Register Number, Subjects Enrolled, Email ID, Phone Number
University: University Name, University ID, Students and Faculties
Department: Department Name, Department ID
Program: Program Name, Program Code, Subjects
Faculties: Name, Subject, Faculty ID
Course: Course Name, Course Code, Credits

## Relationships and Constraints:
Relationship (M:N, Partial Participation)
is in a (M:N, Partial Participation)
provides (M:N, Total Participation from Program side)
contains (M:N, Partial Participation)
Handles (M:N, Partial Participation)
Has (M:N, Partial Participation)

## Extension (Prerequisite / Billing):
Prerequisite: Not modeled in this ER diagram.
Billing: Not modeled in this ER diagram. Can add Billing entity with attributes like Amount, Due Date, Payment Status.

## Design Choices:
Selected Students, Faculties, Departments, Programs, Courses, and University as main entities based on the academic system.

Used M:N relationships for flexibility (students in multiple departments, faculties handling multiple courses).

University connects both students and faculties for organizational clarity.

Subjects are kept as multivalued attributes inside Program for simplicity.

Focused only on academic data; no billing or prerequisites modeled here.

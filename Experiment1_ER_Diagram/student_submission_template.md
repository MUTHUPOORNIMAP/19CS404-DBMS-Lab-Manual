# ER Diagram Submission - Muthu Poornima P 212224240099

## Scenario Chosen: 
University

## ER Diagram:
![ER Diagram](er_diagram.png)
![image](https://github.com/user-attachments/assets/eb81ee5c-e6d6-4946-bd4c-266c8939b8a9)


## Entities and Attributes:
- Entity1: Student Attributes-Name,SubjectS Enrolled,Email ID,DOB,Register Number,Phone Number
- Entity2: University Attributes-University Name,University ID,Students and faculties
- Entity3-Department Attributes-Department Name,Department ID
- Entity4-Program Attributes-Subjects,Program Name,Program Code
- Entity5-Faculties Attributes-Name,Subject,Faculty ID
- Entity6-Course Attributes-Course Code,Course Name,Credits
...

## Relationships and Constraints:
- Relationship1-Relationship(Many-to Many,Student-University)
- Relationship2-Is in a(Many-to Many,Student-Department)
- Relationship3- Provides(Many-to Many,Department-Program)
- Realtionship4- Has(Many-to Many,University-Faculties)
- Realtionship5-Handles(Many-to Many,Faculties-Course)
- Relationship6-Contains(One-to Many,Program-Course)
...

## Extension (Prerequisite / Billing):
- Explain how you modeled prerequisites or billing.
First, a self-referencing M:N relationship called "Prerequisite" would be added within the Course entity, allowing the system to model the dependency between different courses. This ensures that course enrollment rules based on previous completions can be enforced properly. Second, a new entity called "Payment" would be introduced and linked to the Student entity through a One-to-Many relationship. This addition would help track all financial transactions, manage tuition fees, and support billing operations, providing a complete view of the financial obligations of each student. These enhancements would make the model more realistic and capable of supporting a fully functional university management system.

## Design Choices:
Brief explanation of why you chose certain entities, relationships, and assumptions.
I choose entities, relationships, and assumptions based on their relevance to the core functionality and objectives of the system being modeled. Entities represent the key objects or components, such as "Customer" or "Order," that drive the system's processes. Relationships define how these entities interact or depend on each other, ensuring the workflow is captured accurately. Assumptions are made to simplify complex scenarios and focus on what's essential, excluding unnecessary complexity. These choices help in creating a practical, efficient, and scalable system that meets the user's needs while reducing ambiguity.

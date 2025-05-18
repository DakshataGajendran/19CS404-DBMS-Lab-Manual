# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - DAKSHATA G

## Scenario Chosen:
University 

## ER Diagram:
![image](https://github.com/user-attachments/assets/325ba413-c124-4fe9-a57f-b436e1441edc)


## Entities and Attributes:
## STUDENT
Attributes:

admission number

full name

date of birth

contact information:

email

phone number

## INSTRUCTOR
Attributes:

unique staff number

name

contact information:

email

phone number

## COURSES
Attributes:

course number

name

number of credits/units

## PROGRAMS
Attributes:

unique identifier

program name

the governing department

## PREREQUISITE
Attributes:

PrerequisiteID

Course_ID

Relationships and Constraints
## enrolls
Entities Involved: STUDENT ↔ COURSES

Cardinality: Many-to-Many

Participation: Partial

## taught
Entities Involved: INSTRUCTOR ↔ COURSES

Cardinality: Many-to-Many

Participation: Partial

## offers
Entities Involved: PROGRAMS → COURSES

Cardinality: One-to-Many (One program offers many courses)

Participation: Total on COURSES side

## to check
Entities Involved: PREREQUISITE → COURSES

Cardinality: Many-to-One

Participation: Partial

Extension: Prerequisite
The PREREQUISITE entity models prerequisites separately instead of using a recursive relationship on COURSES.

This allows each course to reference multiple prerequisites and enables storing extra metadata in the future (e.g., minimum grade required, reason for prerequisite).

Design Choices
Separate Entities: Each core concept (Student, Instructor, Program, Course) is modeled independently to reflect real-world roles clearly.

Composite Attribute (Contact Information): Groups email and phone logically, avoiding data repetition.

Separate PREREQUISITE Entity: Improves clarity and flexibility, supports expansion (e.g., allowing prerequisites for programs or different course levels).

Clear Relationship Naming: Relationships like enrolls, taught, and offers make the model easier to understand. 

## RESULT

Successfully designed an ER diagram for the University Academic System with entities, relationships, constraints, and optional enhancements to support real-world academic operations.

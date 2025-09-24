
# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram: 
<img width="1251" height="886" alt="Screenshot 2025-09-22 131549" src="https://github.com/user-attachments/assets/2c081437-3e91-4ee6-90e3-374247e2bd51" />


### Entities and Attributes

| Entity | Attributes (PK, FK)| Notes |
|--------|--------------------|-------|
|Members |type,name,date      |       |
|Trainers|name,specifications |       |
|Attendance|session,date,status|      |
|Programs|Program_name        |       |
|Payment |date,amount,method  |       |
|Training|duration,time       |       |
 session                      |       |

### Relationships and Constraints

| Relationship     | Entities Involved             | Cardinality (Min-Max)|
| ---------------- | ----------------------------- | -------------------- |
| **Choose**       | Members ↔ Training Session    | Many-to-Many (M\:N)  |
| **Register**     | Members ↔ Programs            | Many-to-Many (M\:N)  |
| **Assigned\_to** | Trainers ↔ Programs           | Many-to-Many (M\:N)  |
| **Records**      | Attendance ↔ Training Session | Many-to-Many (M\:N)  |
| **Makes**        | Members ↔ Payment             | One-to-Many (1\:M)   |


### Assumptions
```
Members: Each member can choose multiple training sessions (M:N relationship with Choose).
Training Sessions: Each session can have multiple members and multiple trainers.
Trainers: A trainer can be assigned to multiple training sessions (Assigned_to).
Programs: Each program can have multiple sessions, and members can register for multiple programs (Register).
Attendance: Attendance is recorded per session for each member, including status and date.
Payment: Each member can make multiple payments, linked to programs or sessions (Makes).
```
---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_restaurant.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**

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

<img width="1138" height="629" alt="image" src="https://github.com/user-attachments/assets/3614a70f-962b-4dc5-9e29-eed4af292e67" />



### Entities and Attributes

<img width="1082" height="298" alt="image" src="https://github.com/user-attachments/assets/aabea9c4-4261-4996-8a5e-4792bc018eeb" />


### Relationships and Constraints

<img width="1140" height="348" alt="image" src="https://github.com/user-attachments/assets/522b0c10-ee14-401a-9664-dd88b38ec9f9" />


### Assumptions

Each member has a unique member_id.

Programs are predefined (Yoga, Zumba, Weight Training).

A member can join the same program only once at a time.

Each personal training session is handled by only one trainer.

Attendance is mandatory for every booked personal training session.

Payments include both membership fees and personal training session fees.

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

<img width="839" height="644" alt="image" src="https://github.com/user-attachments/assets/95874f12-b5ee-435f-a16f-50c26dbf4d96" />


### Entities and Attributes

<img width="1140" height="387" alt="image" src="https://github.com/user-attachments/assets/62f84092-08a7-4a5a-8d56-50c23ff28eda" />


### Relationships and Constraints



<img width="1139" height="412" alt="image" src="https://github.com/user-attachments/assets/afe89e28-3284-4290-900e-8f0b71cc339f" />

### Assumptions

Each member is uniquely registered.

A member can borrow many books; each loan is for one book.

A book can be loaned many times, but only once at a time.

Loan stores start and return dates.

Fine is generated only for late returns (one fine per loan).

Events can have many speakers and many members.

Each event is booked in one room; rooms can host many events.

Members can attend multiple events.

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

<img width="683" height="689" alt="image" src="https://github.com/user-attachments/assets/fcf718b5-2aa4-4898-a048-9f9ac9aef874" />

### Entities and Attributes

<img width="1140" height="426" alt="image" src="https://github.com/user-attachments/assets/e89f5a81-02be-43b8-bfcf-633477e45ff9" />


### Relationships and Constraints

<img width="1137" height="294" alt="image" src="https://github.com/user-attachments/assets/29101754-06e6-4754-9bf1-08ca5c2e76a6" />


### Assumptions

Each Customer is uniquely identified by Customer_ID.

A customer can place multiple orders, but each order belongs to one customer.

A customer can make multiple reservations.

Each Reservation is for one table at a specific date and time.

A Table can be reserved many times, but only once at a given time.

Each reservation is served by one waiter.

A waiter can serve multiple reservations.

Each reservation generates one bill.

Each bill belongs to one reservation.



---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**

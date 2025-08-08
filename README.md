# MindSched: A Web-Based Mental Health Appointment System

MindSched is a **three-tier web-based application** designed to efficiently manage mental health appointments for **patients**, **psychiatrists**, and **administrative tracking**. The system ensures smooth booking, modification, and cancellation of appointments, secure user authentication, responsive design, and audit logging of all system changes.

---

##  Project Objectives
The aim of MindSched is to:
- **For Patients** – Book, modify, and cancel appointments with mental health consultants.
- **For Doctors (Psychiatrists)** – Manage schedules, update availability, and view patient details.
- **For Admin Tracking** – Store logs of all database changes (insert, update, delete) for auditing.

The system is **scalable**, **user-friendly**, and **responsive** for both desktop and mobile devices.

---

##  Functional Requirements

### User Authentication
- **Registration** – Patients and psychiatrists sign up with basic details (name, email, password, role).
- **Login** – Secure login using Flask-Login with role-based dashboards.

### Appointment Management
- **Book Appointments** – Patients can view available doctors and book based on schedules.
- **Modify / Cancel** – Real-time updates reflected in patient and doctor dashboards.
- **Doctor Availability** – Doctors can set, edit, or delete availability slots.

### Audit Logging
- **Automatic Tracking** – MySQL triggers log every database change with timestamps and action types.

### Responsive UI
- **Custom CSS** – Fully responsive layout for all devices.

---

## Non-Functional Requirements

### Security
- Initial version stores passwords in plain text (future versions to use `bcrypt` hashing).

### Scalability
- MySQL database with indexes on frequently accessed fields (`doctor_id`, `patient_id`, `appointment_id`).

### Performance
- Optimized SQL queries with efficient joins to minimize database hits.

---

##  System Architecture

### Three-Tier Architecture
1. **Presentation Tier** – HTML/CSS frontend.
2. **Business Logic Tier** – Flask routes, authentication, appointment handling.
3. **Data Tier** – MySQL database for users, doctors, patients, and audit logs.

### Key Components
- **User Management** – Role-based authentication and access control.
- **Appointment System** – Booking, updating, deleting appointments.
- **Audit Logging** – Automatic tracking via MySQL triggers.

---

##  Database Design

### Tables
- **Users** – `id`, `username`, `password`, `email`, `role`
- **Doctors** – `id`, `name`, `email`, `specialization`
- **Patients** – `id`, `name`, `appointment_details`, `disease`, `contact_info`
- **Audit Logs** – `log_id`, `action_type`, `user_id`, `timestamp`

### Features
- **Indexes** – For faster query performance.
- **Triggers** – For automatic change logging.

---

##  UML & Workflow

### Class Diagram
- Classes include `User`, `Doctor`, `Patient`, and `Trigger` (Audit Logger).

### Sequence Examples
1. **Patient Booking** – `Frontend → Flask → MySQL → Audit Log`
2. **Doctor Viewing Appointments** – `Frontend → Flask → MySQL`

---

##  Frontend Design

### UI Pages
| Page              | Functionality |
|-------------------|---------------|
| Login / Signup    | Role-based authentication |
| Patient Dashboard | View, book, modify, cancel appointments |
| Doctor Dashboard  | Manage schedules, view patients |
| Audit Logs        | View system activity logs |

### Styling
- **Custom CSS** for flexibility.
- **Media Queries** for mobile responsiveness.

---

##  Challenges and Risks

| Challenge                          | Mitigation Strategy |
|------------------------------------|---------------------|
| Storing passwords securely         | Implement `bcrypt` hashing |
| Preventing double bookings         | Use transaction locks |
| Mobile responsiveness              | Use CSS media queries |
| Tracking appointment changes       | Use MySQL triggers |

---

##  Tools & Technologies

- **Frontend:** HTML, CSS (Custom)
- **Backend:** Python (Flask)
- **Database:** MySQL
- **IDE:** VSCode
- **Libraries:** Flask-Login, SQLAlchemy
- **Version Control:** Git

---


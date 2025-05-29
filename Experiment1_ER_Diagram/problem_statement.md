## Experiment 1: Entity-Relationship (ER) Diagram

### 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

---

### 📚 Purpose:
Gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Chosen Scenario: Hospital Database

Design a database for patient management, appointments, medical records, and billing.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram.
3. Include:
   - Cardinality & participation constraints
   - Billing and payment model
4. Explain:
   - Why entities and relationships were chosen.
   - How billing and payment are modeled.

---

## 👤 Student Name: Charankumar R

## Scenario Chosen: Hospital

## 🗂 ER Diagram:
![image](https://github.com/user-attachments/assets/a3580682-8b5d-4140-adf9-baef17e10952)
---

## 🧾 Entities and Attributes

### 🏥 Patient
- `PatientID` (PK)
- `Name`
- `DateOfBirth`
- `InsuranceDetails`

### 🧑‍⚕️ Doctor
- `DoctorID` (PK)
- `Name`
- `Specialization`

### 🏢 Department
- `DepartmentID` (PK)
- `DepartmentName`
- `DepartmentHead`

### 📅 Appointment
- `AppointmentID` (PK)
- `ReasonForVisit`
- `DateTime`
- `PatientID` (FK)
- `DoctorID` (FK)

### 📋 MedicalRecord
- `RecordID` (PK)
- `Diagnosis`
- `PrescribedMedications`
- `TestResults`
- `AppointmentID` (FK)

### 💳 Billing
- `BillingID` (PK)
- `AppointmentID` (FK)
- `TotalAmount`
- `BillingStatus`

### 💰 Payment
- `PaymentID` (PK)
- `BillingID` (FK)
- `AmountPaid`
- `PaymentDate`
- `PaymentMode`

---

## 🔁 Relationships and Constraints

### Relationships:
- `Patient` ⟷ `Doctor` via `Appointment` (Many-to-Many)
- `Doctor` ⟶ `Department` (Many-to-One)
- `Appointment` ⟶ `MedicalRecord` (One-to-One)
- `Appointment` ⟶ `Billing` (One-to-One)
- `Billing` ⟶ `Payment` (One-to-Many)

### Constraints:
- Each appointment is between one patient and one doctor.
- One bill per appointment.
- A bill can have multiple payments (installments supported).

---

## 💳 Billing & Payment Design

### Billing
- Tracks total amount and payment status.
- Tied directly to an appointment.

### Payment
- Handles actual transactions.
- Allows partial or full payments with different methods (Cash, Card, Online).

---

## 💡 Design Justifications

### Entity Choices:
- **Patient**: Core subject receiving care.
- **Doctor**: Central to service delivery.
- **Department**: Organizes doctors logically.
- **Appointment**: Logs patient-doctor interaction.
- **MedicalRecord**: Stores diagnosis and treatments.
- **Billing**: Tracks financial accountability.
- **Payment**: Enables transaction flexibility.

### Relationship Design:
- Complex relationships (e.g., Patient-Doctor) simplified via `Appointment`.
- Separate billing and payment modules for modularity and scalability.
- Medical data tied to appointments to maintain visit-specific records.

---

## 🔐 Key Assumptions
- Appointments are mandatory for patient visits.
- Each appointment generates one medical record and one bill.
- Payments can be made in parts (installments supported).
- Billing is done even if no charges (e.g., for record-keeping).

---

## ✅ RESULT
Successfully designed an ER diagram for a hospital database covering patients, doctors, departments, appointments, medical records, billing, and payments to support real-world healthcare data management.

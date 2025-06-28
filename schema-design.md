## MySQL Database Design

### Table: appointments
- id: INT, Primary Key, Auto Increment
- doctor_id: INT, Foreign Key → doctors(id)
- patient_id: INT, Foreign Key → patients(id)
- appointment_time: DATETIME, Not Null
- status: INT (0 = Scheduled, 1 = Completed, 2 = Cancelled)
- created_at: DATETIME, NOT NULL DEFAULT CURRENT_TIMESTAMP

---

### Table: patients
- id: INT, Primary Key, Auto Increment
- password: VARCHAR(100), NOT NULL
- email: VARCHAR(100), UNIQUE, NOT NULL
- firstname: VARCHAR(100), NOT NULL
- lastname: VARCHAR(100), NOT NULL
- phone: VARCHAR(20)
- created_at: DATETIME, NOT NULL DEFAULT CURRENT_TIMESTAMP

---

### Table: doctors
- id: INT, Primary Key, Auto Increment
- username: VARCHAR(100), UNIQUE, NOT NULL
- password: VARCHAR(100), NOT NULL
- email: VARCHAR(100), NOT NULL
- firstname: VARCHAR(100), NOT NULL
- lastname: VARCHAR(100), NOT NULL
- specialization: VARCHAR(100), NOT NULL
- bio: VARCHAR(1000)
- phone: VARCHAR(20)
- created_at: DATETIME, NOT NULL DEFAULT CURRENT_TIMESTAMP
- is_active: BOOLEAN DEFAULT TRUE  # For soft deletion

---

### Table: admin
- id: INT, Primary Key, Auto Increment
- username: VARCHAR(100), UNIQUE, NOT NULL
- password: VARCHAR(100), NOT NULL
- email: VARCHAR(100), NOT NULL

---


## MongoDB Collection Design

### Collection: prescriptions

```json
{
  "_id": "ObjectId('64abc123456')",
  "patientId": 42,
  "appointmentId": 51,
  "medication": "Paracetamol",
  "dosage": "500mg",
  "doctorNotes": "Take 1 tablet every 6 hours.",
  "refillCount": 2,
  "pharmacy": {
    "name": "Walgreens SF",
    "location": "Market Street"
  }
}
```
---


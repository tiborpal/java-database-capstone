## User Story Template

**Title:**
_As a [user role], I want [feature/goal], so that [reason]._

**Acceptance Criteria:**
1. [Criteria 1]
2. [Criteria 2]
3. [Criteria 3]

**Priority:** [High/Medium/Low]
**Story Points:** [Estimated Effort in Points]
**Notes:**
- [Additional information or edge cases]

---

## Admin User Stories

### User Story: Admin Login and Secure Platform Management

**Title:** Admin Login and Secure Platform Management

**As an admin**, I want to **log into the platform securely with my username and password**, so that **I can manage the platform.**

**Acceptance Criteria:**
1. The admin can access the login page.
2. The system authenticates the admin's username and password against registered credentials.
3. Upon successful authentication, the admin is redirected to the platform management dashboard.
4. Upon unsuccessful authentication (e.g., incorrect credentials), an error message is displayed, and the admin remains on the login page.

**Priority:** High

**Story Points:** 3

**Notes:**
- Session management should be secure to prevent unauthorized access after an admin logs in.

---

### User Story: Admin Logout

**Title:** Admin Logout

**As an admin**, I want to **log out of the portal**, so that **I can protect system access.**

**Acceptance Criteria:**
1. The admin can initiate a logout action from anywhere within the authenticated portal.
2. Upon logout, the admin's session is terminated.
3. The admin is redirected to the login page or a public landing page.
4. Attempting to access previously authenticated pages after logout requires re-authentication.

**Priority:** High

**Story Points:** 1

**Notes:**
- A clear and easily accessible logout button should be present on all authenticated pages.
- The system should confirm successful logout to the admin.

---

### User Story: Add Doctors to the Portal

**Title:** Add Doctors to the Portal

**As an admin**, I want to **add doctors to the portal**, so that **new medical professionals can be managed within the system.**

**Acceptance Criteria:**
1. The admin can access a dedicated "Add Doctor" interface.
2. The admin can input required doctor information (e.g., name, specialization, contact details).
3. The system validates the input data for correctness and completeness.
4. Upon successful submission, the new doctor's profile is created and visible in the doctor management section.
5. The admin receives a confirmation of the doctor's successful addition.

**Priority:** Medium

**Story Points:** 5

**Notes:**
- Consider unique identifiers for doctors (e.g., employee ID, national registration number).
- Determine which fields are mandatory and which are optional.
- Error handling for duplicate entries or invalid data should be implemented.

---

### User Story: Delete Doctor's Profile

**Title:** Delete Doctor's Profile

**As an admin**, I want to **delete a doctor's profile from the portal**, so that **outdated or incorrect doctor information can be removed.**

**Acceptance Criteria:**
1. The admin can select an existing doctor's profile for deletion.
2. The system prompts for confirmation before permanently deleting a doctor's profile.
3. Upon confirmation, the doctor's profile and associated data (if applicable and specified) are removed from the system.
4. The admin receives a confirmation of the doctor's successful deletion.
5. The deleted doctor's profile is no longer visible in the doctor management section.

**Priority:** Medium

**Story Points:** 3

**Notes:**
- Consider the implications of deleting a doctor's profile on historical data (e.g., past appointments). Should appointments be re-assigned or simply marked as associated with a deleted doctor?
- Implement soft deletion as an alternative to hard deletion, where profiles are marked as inactive rather than permanently removed.

---

### User Story: Track Usage Statistics (Appointments per Month)

**Title:** Track Usage Statistics (Appointments per Month)

**As an admin**, I want to **run a stored procedure in MySQL CLI to get the number of appointments per month**, so that **I can track usage statistics.**

**Acceptance Criteria:**
1. The admin has the necessary credentials and permissions to access the MySQL CLI.
2. A stored procedure exists in the database that accurately calculates the number of appointments per month.
3. The admin can successfully execute the stored procedure from the MySQL CLI.
4. The output of the stored procedure clearly displays the count of appointments for each month.
5. The data provided by the stored procedure is accurate and up-to-date.

**Priority:** Low

**Story Points:** 2

**Notes:**
- Documentation should be available for the stored procedure, including its name, parameters (if any), and expected output format.

---

## Patient User Stories

### User Story: Patient View Doctor List (Pre-Login)

**Title:** Patient View Doctor List (Pre-Login)

**As a patient**, I want to **view a list of doctors without logging in**, so that **I can explore options before registering.**

**Acceptance Criteria:**
1. The patient can access a public-facing section of the portal that displays doctor information.
2. The list includes essential doctor details (e.g., name, specialization, possibly availability or a brief bio).
3. The patient is not required to provide login credentials to view this information.
4. The list is filterable and/or searchable by criteria such as specialization or name (optional but good for usability).

**Priority:** High

**Story Points:** 3

**Notes:**
- Ensure privacy compliance for any displayed doctor information.

---

### User Story: Patient Sign Up

**Title:** Patient Sign Up

**As a patient**, I want to **sign up using my email and password**, so that **I can book appointments.**

**Acceptance Criteria:**
1. The patient can access a dedicated registration page.
2. The system prompts for a valid email address, password, and password confirmation.
3. The system validates the input for email format and password strength requirements.
4. Upon successful registration, a new patient account is created.
5. The patient receives a confirmation of successful registration (e.g., an email verification link or immediate login).
6. The patient is able to log in with the newly created credentials.

**Priority:** High

**Story Points:** 5

**Notes:**
- Implement email verification to ensure valid email addresses.
- Define strong password policy requirements (e.g., minimum length, special characters).

---

### User Story: Patient Login and Booking Management

**Title:** Patient Login and Booking Management

**As a patient**, I want to **log into the portal**, so that **I can manage my bookings.**

**Acceptance Criteria:**
1. The patient can access the login page.
2. The system authenticates the patient's email and password against registered credentials.
3. Upon successful authentication, the patient is redirected to their personal dashboard or booking management section.
4. Upon unsuccessful authentication (e.g., incorrect credentials), an error message is displayed, and the patient remains on the login page.
5. The login process uses secure communication (e.g., HTTPS).

**Priority:** High

**Story Points:** 3

**Notes:**
- Ensure secure session management.

---

### User Story: Patient Logout

**Title:** Patient Logout

**As a patient**, I want to **log out of the portal**, so that **I can secure my account.**

**Acceptance Criteria:**
1. The patient can initiate a logout action from anywhere within their authenticated portal.
2. Upon logout, the patient's session is terminated.
3. The patient is redirected to the login page or a public landing page.
4. Attempting to access previously authenticated pages after logout requires re-authentication.

**Priority:** High

**Story Points:** 1

**Notes:**
- A clear and easily accessible logout option should be present on all authenticated pages.
- The system should confirm successful logout to the patient.

---

### User Story: Patient Book Hour-Long Appointment

**Title:** Patient Book Hour-Long Appointment

**As a patient**, I want to **log in and book an hour-long appointment to consult with a doctor**, so that **I can get medical advice.**

**Acceptance Criteria:**
1. The patient can access the appointment booking interface after logging in.
2. The patient can select a doctor from the available list.
3. The booking interface clearly shows available time slots for doctors.
4. The patient can specify or select an appointment duration of one hour.
5. The system confirms the appointment booking to the patient (e.g., on-screen message, email confirmation).
6. The system updates the doctor's availability accordingly.

**Priority:** High

**Story Points:** 8

**Notes:**
- Integration with doctor's availability schedules is critical.
- The system should prevent double-booking or booking unavailable slots.

---

### User Story: Patient View Upcoming Appointments

**Title:** Patient View Upcoming Appointments

**As a patient**, I want to **view my upcoming appointments**, so that **I can prepare accordingly.**

**Acceptance Criteria:**
1. The patient can access a dedicated section of the portal to view their appointments after logging in.
2. The list clearly displays details for each upcoming appointment (e.g., doctor's name, date, time, duration).
3. The list is organized chronologically.
4. The patient can easily identify the status of each appointment (e.g., confirmed, pending).
5. The patient has options to cancel or reschedule appointments (if allowed by system rules).

**Priority:** Medium

**Story Points:** 3

**Notes:**
- Clear indicators for any necessary pre-appointment preparations (e.g., bringing documents).

---

## Doctor User Stories

### User Story: Doctor Login and Appointment Management

**Title:** Doctor Login and Appointment Management

**As a doctor**, I want to **log into the portal**, so that **I can manage my appointments.**

**Acceptance Criteria:**
1. The doctor can access the login page.
2. The system authenticates the doctor's username and password against registered credentials.
3. Upon successful authentication, the doctor is redirected to their appointment management dashboard.
4. Upon unsuccessful authentication (e.g., incorrect credentials), an error message is displayed, and the doctor remains on the login page.

**Priority:** High

**Story Points:** 3

**Notes:**
- Ensure secure session management.

---

### User Story: Doctor Logout

**Title:** Doctor Logout

**As a doctor**, I want to **log out of the portal**, so that **I can protect my data.**

**Acceptance Criteria:**
1. The doctor can initiate a logout action from anywhere within their authenticated portal.
2. Upon logout, the doctor's session is terminated.
3. The doctor is redirected to the login page or a public landing page.
4. Attempting to access previously authenticated pages after logout requires re-authentication.

**Priority:** High

**Story Points:** 1

**Notes:**
- A clear and easily accessible logout option should be present on all authenticated pages.
- The system should confirm successful logout to the doctor.

---

### User Story: Doctor View Appointment Calendar

**Title:** Doctor View Appointment Calendar

**As a doctor**, I want to **view my appointment calendar**, so that **I can stay organized.**

**Acceptance Criteria:**
1. The doctor can access a calendar view showing their scheduled appointments.
2. The calendar clearly displays appointment details (e.g., patient name, time, duration).
3. The doctor can easily navigate between different dates.
4. The calendar clearly distinguishes between confirmed and pending appointments.

**Priority:** High

**Story Points:** 5

**Notes:**
- Provide options to filter appointments (e.g., by type, status).

---

### User Story: Doctor Mark Unavailability

**Title:** Doctor Mark Unavailability

**As a doctor**, I want to **mark my unavailability**, so that **patients are only informed of available slots.**

**Acceptance Criteria:**
1. The doctor can access an interface to specify periods of unavailability (e.g., specific dates, recurring blocks of time).
2. The system allows the doctor to provide a reason for unavailability (optional).
3. Once marked unavailable, these slots are not shown as bookable to patients.
4. The doctor can easily remove or modify marked unavailability.

**Priority:** Medium

**Story Points:** 5

**Notes:**
- Ensure this feature integrates seamlessly with the patient booking process.

---

### User Story: Doctor Update Profile Information

**Title:** Doctor Update Profile Information

**As a doctor**, I want to **update my profile with specialization and contact information**, so that **patients have up-to-date information.**

**Acceptance Criteria:**
1. The doctor can access an interface to edit their profile details.
2. The doctor can modify their specialization, contact information (e.g., phone, email), and possibly a brief bio or photo.
3. The system validates the input data for correctness (e.g., email format).
4. Upon successful submission, the updated information is reflected in their public profile.
5. Patients viewing the doctor's profile see the latest information.

**Priority:** Medium

**Story Points:** 4

**Notes:**
- Clearly define which fields are editable by the doctor.
- Ensure profile changes are immediately visible to patients.

---

### User Story: Doctor View Patient Details for Upcoming Appointments

**Title:** Doctor View Patient Details for Upcoming Appointments

**As a doctor**, I want to **view the patient details for upcoming appointments**, so that **I can be prepared.**

**Acceptance Criteria:**
1. The doctor can access patient details directly from their appointment calendar or a dedicated list of upcoming appointments.
2. For each upcoming appointment, the system displays relevant patient information (e.g., patient name, contact details, reason for visit, medical history summary if available and permitted).
3. The doctor can easily navigate between different patient profiles for their appointments.

**Priority:** High

**Story Points:** 6

**Notes:**
- Strict security and access controls are paramount for patient data.
- Clearly define what patient information is accessible to the doctor and what requires additional consent or access levels.



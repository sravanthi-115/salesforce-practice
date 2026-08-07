# 🎓 Salesforce Placement Management System
## 📅 Sprint 5 – Making Software Talk to Data (SOQL, DML & Apex)

---

# 📌 Project Overview

This project extends the **Salesforce Placement Management System** by implementing complete business transactions using **SOQL**, **DML**, and **Apex**. The application retrieves business data, validates eligibility rules, prevents duplicate applications, creates new records, updates existing records, and returns meaningful responses to users.

The implementation follows Salesforce engineering principles by retrieving only the required information, validating business rules before modifying data, and keeping the code modular and maintainable.

---

# 🚀 Technologies Used

- ☁️ Salesforce CRM
- 💻 Apex Classes
- 🔍 SOQL (Salesforce Object Query Language)
- 💾 DML (Data Manipulation Language)
- 📦 Custom Objects
- ⚙️ Developer Console

---

# 📂 Custom Objects

- 👨‍🎓 Student
- 💼 Job
- 📝 Application
- 📄 Offer Letter

---

# 🏗️ Apex Classes

### 👨‍🎓 StudentService

Responsible for retrieving student information required for eligibility validation.

**Method**

```apex
getStudent(Id studentId)
```

---

### 💼 JobService

Responsible for retrieving job eligibility details.

**Method**

```apex
getJob(Id jobId)
```

---

### 📝 ApplicationService

Responsible for application processing.

**Methods**

```apex
isDuplicateApplication()

createApplication()

updateApplicationStatus()

submitApplication()
```

---

# 🔍 SOQL Implementation

The following SOQL queries were implemented during the project.

### ✅ Retrieve Student Information

Purpose:

Retrieve only the fields required for eligibility checking.

Retrieved Fields

- Student Name
- CGPA
- Email

---

### ✅ Retrieve Job Information

Purpose:

Retrieve only the fields required before validating an application.

Retrieved Fields

- Job Name
- Minimum CGPA
- Closing Date

---

### ✅ Check Duplicate Application

Purpose:

Verify whether the student has already applied for the selected job.

If a matching Application record exists, the system prevents duplicate submissions.

---

# 💾 DML Operations

### ✅ Create Application

A new Application record is created after:

- Student information is retrieved
- Job information is retrieved
- Eligibility is validated
- Duplicate application is checked

---

### ✅ Update Application Status

Existing Application records can be updated to:

- Applied
- Shortlisted
- Interview Scheduled
- Selected
- Rejected

---

# 🔄 Complete Business Transaction

The application follows the sequence below for every application request.

```text
Student Request
      │
      ▼
Retrieve Student
      │
      ▼
Retrieve Job
      │
      ▼
Validate Eligibility
      │
      ▼
Check Duplicate Application
      │
      ▼
Create Application Record
      │
      ▼
Save Record
      │
      ▼
Return Confirmation
```

This sequence ensures that business rules are validated before any changes are made to Salesforce records.

---

# 📋 User Stories Implemented

| User Story | Status |
|------------|--------|
| ✅ Retrieve Student Information | Completed |
| ✅ Retrieve Job Eligibility | Completed |
| ✅ Prevent Duplicate Applications | Completed |
| ✅ Create Application Record | Completed |
| ✅ Update Application Status | Completed |
| ✅ Return Meaningful Feedback | Completed |

---

# 🏛️ Engineering Principles Followed

### 🔹 Retrieve Only Required Information

Only the fields required for the current business decision are retrieved.

Benefits:

- Better Performance
- Reduced Resource Usage
- Cleaner Code

---

### 🔹 Validate Before DML

Business rules are validated before performing INSERT or UPDATE operations.

This prevents:

- Invalid Applications
- Duplicate Records
- Incorrect Business Data

---

### 🔹 Single Responsibility Principle

Each Apex class performs one responsibility.

| Class | Responsibility |
|--------|---------------|
| StudentService | Student Retrieval |
| JobService | Job Retrieval |
| ApplicationService | Application Processing |

---

# 🎯 Business Rules Implemented

- ✅ Retrieve Student Details
- ✅ Retrieve Job Details
- ✅ Check Student Eligibility
- ✅ Check Duplicate Applications
- ✅ Create Application
- ✅ Update Application Status
- ✅ Display Appropriate Success/Error Messages

---

# 💡 SOQL vs DML

| SOQL | DML |
|------|-----|
| Retrieves information | Modifies information |
| Read Operation | Create, Update, Delete |
| Used before business decisions | Used after business validation |

---

# 🎤 Interview Questions & Answers

## ❓What is SOQL?

SOQL (Salesforce Object Query Language) is used to retrieve records from Salesforce objects based on business requirements.

---

## ❓What is DML?

DML (Data Manipulation Language) is used to create, update, delete, or restore Salesforce records.

---

## ❓Why is SOQL executed before DML?

SOQL retrieves the information required to make business decisions. After all validations are completed successfully, DML modifies the data.

---

## ❓Why should we retrieve only required fields?

Retrieving unnecessary fields increases resource usage and reduces application performance.

---

## ❓Why should DML occur only after business validation?

Performing DML before validation may result in invalid or duplicate records being stored in Salesforce.

---

## ❓Why separate StudentService, JobService and ApplicationService?

Separating responsibilities makes the code easier to understand, maintain, test, and extend.

---

# 📊 Features Implemented

- 🔍 Student Information Retrieval
- 🔍 Job Information Retrieval
- 🚫 Duplicate Application Prevention
- 💾 Application Creation
- 🔄 Application Status Update
- 📩 User Confirmation Messages

---

# 📷 Screenshots Included

### 📸 Sprint 7 – Retrieve Student Information

### 📸 Sprint 8 – Retrieve Job Information

### 📸 Sprint 9 – Prevent Duplicate Applications

### 📸 Sprint 10 – Create Application Record

### 📸 Sprint 11 – Update Application Status

### 📸 Sprint 12 – Complete Business Transaction

---

# 🎓 Learning Outcomes

Through this sprint, I learned how to:

- ✅ Retrieve Salesforce records using SOQL
- ✅ Create and update records using DML
- ✅ Build reusable Apex service classes
- ✅ Design complete business transactions
- ✅ Prevent duplicate applications
- ✅ Apply business validation before modifying data
- ✅ Follow clean coding and engineering principles
- ✅ Build maintainable Salesforce applications

---

# 📤 Assignment Questions

## ❓1. Why is SOQL required?

SOQL is required to retrieve the business information needed before making decisions. It allows the application to fetch only the required records from Salesforce.

---

## ❓2. Why is DML required?

DML is required to create new records or update existing records after all business validations have been completed successfully.

---

## ❓3. Why should software retrieve information before making decisions?

Business decisions depend on accurate information. Without retrieving the required data, the software cannot validate eligibility, check duplicates, or process applications correctly.

---

## ❓4. When should new records be created?

A new Application record should be created only after all business rules have been validated successfully.

---

## ❓5. When should existing records be updated?

Existing records should be updated when business information changes, such as updating an Application Status after the recruitment process.

---

## ❓6. Why should data changes always follow business validation?

Business validation prevents invalid or duplicate records from being stored and ensures that only correct information is saved in Salesforce.

---
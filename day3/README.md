# 🎓 Salesforce Placement Management System

## 📅 Day 3 Assignment – Validation Rules, Flows & Triggers

---

## 📌 Project Overview

This project enhances the **Salesforce Placement Management System** by implementing automation using **Record-Triggered Flows** and **Validation Rules**. The solution improves data quality, automates business processes, and follows Salesforce's declarative development approach.

---

# 🚀 Technologies Used

- ☁️ Salesforce CRM
- 🔄 Flow Builder
- ✅ Validation Rules
- 📧 Email Alerts
- 📦 Custom Objects
- ⚙️ Record-Triggered Flows

---

# 📂 Custom Objects

- 👨‍🎓 Student
- 💼 Job
- 📝 Application
- 📄 Offer Letter

---

# 🔗 Object Relationships

- Application ➜ Student (Lookup)
- Application ➜ Job (Lookup)
- Offer Letter ➜ Student (Lookup)
- Offer Letter ➜ Job (Lookup)
- Offer Letter ➜ Application (Lookup)

---

# 🔄 Record-Triggered Flows

## ✅ Flow 1 – Auto Populate Application Date

**Object:** Application

**Trigger:** Record Created

**Type:** Before Save

### Purpose

Automatically fills the **Application Date** whenever a new Application record is created.

---

## ✅ Flow 2 – Send Email Notification

**Object:** Application

**Trigger:** Record Created

**Type:** After Save

### Purpose

Automatically sends an email notification to the Placement Officer whenever a student submits an application.

---

## ✅ Flow 3 – Create Offer Letter

**Object:** Application

**Trigger:** Record Updated

**Condition:** Status = Selected

**Type:** After Save

### Purpose

Automatically creates an **Offer Letter** record whenever an application's status changes to **Selected**.

---

# ✅ Validation Rules

## 1️⃣ Prevent Application After Job Closing Date

### Formula

```text
Application_Date__c > Job__r.Closing_Date__c
```

### Purpose

Prevents students from applying after the job closing date.

---

## 2️⃣ Reject Low CGPA Applications

### Formula

```text
Student__r.CGPA__c < Job__r.Minimum_CGPA__c
```

### Purpose

Prevents students from applying if their CGPA is below the minimum CGPA required for the job.

---

## 3️⃣ Mandatory Fields Validation

### Formula

```text
OR(
ISBLANK(Student__c),
ISBLANK(Job__c),
ISBLANK(TEXT(Status__c)),
ISBLANK(Application_Date__c)
)
```

### Purpose

Ensures all mandatory fields are completed before saving the Application record.

---

# 📋 Business Requirements & Solutions

| Requirement                       | Solution                                       |
| --------------------------------- | ---------------------------------------------- |
| 📅 Auto-fill Application Date     | ✅ Before-Save Flow                            |
| 📧 Send Email Notification        | ✅ After-Save Flow                             |
| 📄 Create Offer Letter            | ✅ After-Save Flow                             |
| 🎯 Reject Low CGPA                | ✅ Validation Rule                             |
| ⏰ Prevent Late Applications      | ✅ Validation Rule                             |
| 📝 Mandatory Fields               | ✅ Validation Rule                             |
| 🚫 Prevent Duplicate Applications | ⚠️ Duplicate Rule / Apex Trigger (Recommended) |

---

# 💡 Why These Solutions?

### 🔄 Why Flow?

- No coding required
- Easy to maintain
- Faster than Apex for simple automation
- Recommended by Salesforce

### ✅ Why Validation Rules?

- Prevent invalid data
- Improve data quality
- Stop incorrect records before saving

### 💻 Why Apex for Duplicate Applications?

Validation Rules cannot compare the current record with existing records in the database. Duplicate Rules or Apex Triggers are the appropriate solutions.

---

# 🎯 Interview Questions

### ✔ What is a Validation Rule?

A Validation Rule ensures only valid data is saved in Salesforce by preventing records that violate business rules.

---

### ✔ What is a Flow?

A Flow is Salesforce's declarative automation tool used to automate business processes without writing code.

---

### ✔ What is an Apex Trigger?

An Apex Trigger is custom code that executes before or after database events such as Insert, Update, Delete, or Undelete.

---

### ✔ Why use Flow instead of Apex?

Flow was sufficient for this project because all required automation could be achieved without writing code. It is easier to build, maintain, and follows Salesforce best practices.

---

# 📈 Project Features

- ✅ Automatic Application Date
- ✅ Email Notification
- ✅ Offer Letter Generation
- ✅ Low CGPA Validation
- ✅ Job Closing Date Validation
- ✅ Mandatory Field Validation

---

# 📷 Screenshots Included

- 📸 Flow 1 – Auto Populate Application Date
- 📸 Flow 2 – Send Email Notification
- 📸 Flow 3 – Create Offer Letter
- 📸 Validation Rule 1 – Prevent Application After Closing Date
- 📸 Validation Rule 2 – Reject Low CGPA
- 📸 Validation Rule 3 – Mandatory Fields Validation

---

# 🎓 Learning Outcome

Through this assignment, I learned how to:

- Build Record-Triggered Flows
- Implement Validation Rules
- Automate business processes
- Improve data quality
- Choose between Flow, Validation Rules, and Apex based on business requirements
- Apply Salesforce declarative automation best practices

---

# 📤 Assignment Questions

## ❓1. Which requirements did you solve using Flow?

The following requirements were implemented using **Record-Triggered Flows**:

- 📅 Automatically populate the **Application Date** when a new Application record is created (Before-Save Flow).
- 📧 Send an **Email Notification** to the Placement Officer whenever a student submits an application (After-Save Flow).
- 📄 Automatically **Create an Offer Letter** record when the Application Status changes to **Selected** (After-Save Flow).

---

## ❓2. Which requirements required Validation Rules?

The following requirements were implemented using **Validation Rules**:

- 🎯 Prevent students from applying if their **CGPA is below the Job's Minimum CGPA**.
- ⏰ Prevent students from submitting an application **after the Job Closing Date**.
- 📝 Ensure that **mandatory fields are not left blank** before saving the Application record.

---

## ❓3. Which requirements still needed Apex?

The requirement to **prevent duplicate applications** could not be implemented using a Validation Rule because Validation Rules cannot compare the current record with existing records in the database.

This requirement is best implemented using:

- ✅ Salesforce Duplicate Rules (Recommended)
- ✅ Apex Trigger (for more complex business logic)

---

## ❓4. Why did you choose those solutions?

I selected **Record-Triggered Flows** for automation tasks such as updating fields, sending emails, and creating related records because they are declarative, easy to maintain, and recommended by Salesforce.

I used **Validation Rules** to enforce business rules and maintain data quality by preventing invalid records from being saved.

For duplicate application prevention, I recommended **Duplicate Rules or Apex Trigger** because declarative validation cannot compare records across the database. This approach follows Salesforce's best practice of using **Clicks before Code**.

## ⭐ Conclusion

This project successfully automated the Placement Management System using Salesforce's declarative tools. Business processes such as application date population, email notifications, offer letter generation, and data validation were implemented without Apex wherever possible, following Salesforce best practices.

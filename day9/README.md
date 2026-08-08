# 🎓 Salesforce Placement Management System

## 📅 Sprint 9 Assignment – Lightning Web Components & Interactive User Experience

---

# 📌 Project Overview

This assignment focused on building **user-facing experiences using Lightning Web Components (LWC)** for the Salesforce Placement Management System.

The objective was to connect the existing Salesforce backend architecture with a simple student interface where students can **view eligible jobs, view details, and apply for opportunities** while keeping business logic inside the service layer.

---

# 🚀 Technologies Used

* ☁️ Salesforce CRM
* ⚡ Lightning Web Components
* 💻 JavaScript
* 🌐 HTML
* 🔧 Apex
* 🧠 Service Classes
* 🔍 SOQL
* 💾 DML
* 🔄 Wire Service
* 📡 Lightning Data Service
* 🧩 Custom Events

---

# 📂 Components Used

* 👨‍🎓 Student Summary
* 💼 Eligible Jobs
* 📝 Job Card
* 📊 My Applications
* 🏆 Offer Summary

The Sprint describes these as the planned components of the Student Placement Portal.

---

# 🎯 Learning Objectives

During this assignment, I learned to:

* ✅ Understand Lightning Web Components
* ✅ Design components around user capabilities
* ✅ Use HTML for presentation
* ✅ Use JavaScript for component behaviour
* ✅ Understand data binding
* ✅ Handle user events
* ✅ Retrieve Salesforce data
* ✅ Understand Lightning Data Service and Wire Service
* ✅ Call Apex imperatively
* ✅ Keep business logic outside the UI
* ✅ Build parent-child components
* ✅ Communicate using custom events
* ✅ Handle loading, success, empty and error states
* ✅ Refresh the UI after data changes

---

# 🔄 Sprint 23 – Build Eligible Jobs Component

## 📌 Business Requirement

Students should be able to open the Placement Portal and view jobs for which they are eligible.

The job information includes:

* 🏢 Company
* 💼 Role
* 💰 Package
* 📍 Location
* 📅 Deadline
* 🔍 View Details

The component should retrieve real Salesforce data and connect with the existing eligibility logic.

### Workflow

```text
👨‍🎓 Student
      ↓
💼 Eligible Jobs LWC
      ↓
☁️ Apex / Data Service
      ↓
🧠 Eligibility Logic
      ↓
🗄️ Salesforce Data
      ↓
📋 Display Eligible Jobs
```

---

# 🔄 Sprint 24 – Build Apply Workflow

## 📌 Business Requirement

A student viewing an eligible job should be able to submit an application.

### Apply Workflow

```text
🖱️ Click Apply
      ↓
⚡ LWC Event
      ↓
📌 Identify Job Id
      ↓
☁️ Imperative Apex
      ↓
🧠 Application Service
      ↓
🔎 Check Duplicate
      ↓
✅ Validate Eligibility
      ↓
💾 Create Application
      ↓
📤 Return Result
      ↓
🔄 Update UI
```

The Apply workflow connects the user interface with the existing Apex and business-service architecture.

---

# 🔄 Sprint 25 – Design Apply States

The application should clearly communicate what is happening after the student clicks **Apply**.

### Four Apply States

```text
1️⃣ [ APPLY ]

2️⃣ [ ⏳ SUBMITTING... ]

3️⃣ [ ✅ APPLICATION SUBMITTED ]

4️⃣ [ ⚠️ APPLICATION COULD NOT BE SUBMITTED ]
```

The UI should also prevent accidental repeated submissions while the request is processing.

---

# 🔄 Sprint 26 – Component Communication

## 📌 Business Requirement

The Eligible Jobs interface should be divided into smaller components instead of creating one large component.

### Component Structure

```text
Eligible Jobs
     ↓
  Job Card
```

### Parent → Child

The parent passes job information to the child using public properties such as `@api`.

```text
Parent
  ↓
Job Information
  ↓
Child
```

### Child → Parent

The child communicates user actions using **Custom Events**.

```text
Child
  ↓
Custom Event
  ↓
Parent
  ↓
Handle Action
```

This keeps components focused and loosely coupled.

---

# 📋 Business Requirements & Solutions

| Requirement                    | Solution                  |
| ------------------------------ | ------------------------- |
| Display eligible jobs          | ⚡ Lightning Web Component |
| Retrieve Salesforce data       | 🔄 Wire / LDS / Apex      |
| Handle Apply action            | 🖱️ LWC Event             |
| Submit application             | ☁️ Imperative Apex        |
| Protect business rules         | 🧠 Service Layer          |
| Prevent duplicate applications | 🔐 Backend validation     |
| Prevent repeated clicks        | ⏳ Processing state        |
| Communicate child actions      | 📡 Custom Events          |
| Keep UI updated                | 🔄 Refresh / State Update |
| Handle failures                | ⚠️ Error State            |

---

# 💡 Why These Solutions?

## ⚡ Why Lightning Web Components?

LWC provides the user-facing layer of the Salesforce application and allows users to interact with the business capabilities built in the backend.

---

## 🔄 Why Wire Service?

Wire-based approaches are useful for **reactive data requirements**, allowing the component to respond when relevant data becomes available or changes.

---

## ⚡ Why Imperative Apex?

Application submission begins because the **student explicitly clicks Apply**, so the component needs control over when the Apex method executes.

---

## 🧠 Why Keep Business Logic in Apex?

Eligibility rules should not be duplicated inside JavaScript.

The UI should request:

> Student wants to apply for this job.

The business layer decides whether the request is valid.

This allows the same rules to be reused by other entry points such as APIs, batch jobs and integrations.

---

## 🧩 Why Parent-Child Components?

Large interfaces become difficult to maintain when everything is placed inside one component.

Separating meaningful responsibilities such as **Job Card** and **Job Filters** makes the interface easier to understand and maintain.

---

# 📊 UI States

Every data-driven interface should consider:

| State     | Example                    |
| --------- | -------------------------- |
| ⏳ Loading | Data is being retrieved    |
| ✅ Success | Jobs are displayed         |
| 📭 Empty  | No eligible jobs available |
| ⚠️ Error  | Something went wrong       |

The sprint emphasizes designing the complete experience rather than only the successful state.

---

# 📋 Key Engineering Principles

* ✅ Start with the user's requirement.
* ✅ Components should represent user capabilities.
* ✅ Keep each component focused.
* ✅ Keep business rules outside the UI.
* ✅ Use imperative Apex for explicit user actions.
* ✅ Use events for component communication.
* ✅ Prevent accidental duplicate actions.
* ✅ Backend validation protects data integrity.
* ✅ Frontend behaviour protects user experience.
* ✅ Refresh or update stale UI data after mutations.
* ✅ Debug by following the data flow instead of guessing.

---

# 🎯 Questions

## 1️⃣ What is Lightning Web Components?

Lightning Web Components are Salesforce components used to build interactive user experiences. They provide the user-facing layer that connects users with Salesforce business capabilities.

---

## 2️⃣ What did you build?

I designed a **Student Placement Portal** with an Eligible Jobs component and an interactive Apply workflow using LWC, Apex and Salesforce data services.

---

## 3️⃣ What is the difference between Wire and Imperative Apex?

**Wire** is commonly used for reactive data requirements, while **imperative Apex** provides explicit control over when server-side functionality is executed, such as when a student clicks Apply.

---

## 4️⃣ How does a child communicate with a parent?

A child component can communicate with its parent by dispatching a **Custom Event** containing relevant information such as the Job Id.

---

## 5️⃣ Why should business logic not be written in JavaScript?

Business rules should remain in the service layer so they can be reused by different entry points and are not dependent on a particular user interface.

---

## 6️⃣ How do you prevent duplicate Apply clicks?

The frontend can disable the Apply button or display a processing state while the request is running, while backend validation protects the data from duplicate applications.

---

# 📈 Project Features

* ✅ Eligible Jobs LWC
* ✅ Job Card Component
* ✅ Data Binding
* ✅ Salesforce Data Retrieval
* ✅ Wire Service
* ✅ Lightning Data Service Concepts
* ✅ Imperative Apex
* ✅ Apply Workflow
* ✅ Parent-Child Communication
* ✅ Custom Events
* ✅ Loading / Success / Empty / Error States
* ✅ Duplicate Submission Protection
* ✅ UI Refresh

---

# 🎓 Learning Outcomes

Through this assignment, I learned how to:

* ⚡ Build interactive Lightning Web Components
* 🎨 Design interfaces around user needs
* 🔄 Work with reactive data
* 🖱️ Handle user interactions
* ☁️ Connect LWC with Apex
* 🧠 Separate UI and business logic
* 🧩 Design parent-child components
* 📡 Use custom events for communication
* 🔄 Manage changing and stale data
* 🐛 Debug an end-to-end request
* 🏗️ Think about UI as part of a larger software architecture

---


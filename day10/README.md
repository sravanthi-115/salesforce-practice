# 🎓 Salesforce Placement Management System

## 📅 Day 10 Assignment – Component Communication, Forms, LDS & Reusable LWC Architecture

---

# 📌 Project Overview

This assignment focused on building a **well-structured Lightning Web Component architecture** for the Salesforce Placement Management System.

The objective was to understand how multiple LWCs can work together as one application using **parent-child communication, custom events, forms, Lightning Data Service, reactive data, and reusable components**.

---

# 🚀 Technologies Used

- ☁️ Salesforce CRM
- ⚡ Lightning Web Components
- 💻 JavaScript
- 🌐 HTML
- 🔧 Apex
- 📡 Lightning Data Service
- 🔄 Reactive Data
- 🧩 Custom Events
- 📝 Lightning Base Components
- 🔍 SOQL
- 🏗️ Component Architecture

---

# 📂 Components Used

- 👨‍🎓 Student Summary
- 👤 Student Profile
- 💼 Eligible Jobs
- 💳 Job Card
- 📝 My Applications
- 📄 Application Card
- 🏆 Offer Summary
- 🏷️ Status Badge
- 📭 Empty State

The Day 10 architecture expands the portal into focused components with clear responsibilities.

---

# 🎯 Learning Objectives

During this assignment, I learned to:

- ✅ Design multiple LWCs as one application
- ✅ Understand parent-to-child communication
- ✅ Understand child-to-parent communication
- ✅ Use `@api` properties
- ✅ Use custom events
- ✅ Build forms using Lightning base components
- ✅ Perform client-side validation
- ✅ Understand server-side validation
- ✅ Use Lightning Data Service
- ✅ Understand reactive data and refresh
- ✅ Create reusable components
- ✅ Design loading, success, empty and error states
- ✅ Avoid large "God Components"
- ✅ Reduce unnecessary component coupling

---

# 🔄 Sprint 27 – Component Communication

## 📌 Business Requirement

The Student Placement Portal contains multiple components that need to communicate with each other.

### Component Structure

```text
StudentPortal
│
├── StudentSummary
├── EligibleJobs
│   └── JobCard
├── MyApplications
│   └── ApplicationCard
└── OfferSummary
```

Each component has a clear responsibility, while communication keeps the complete application connected.

### Parent → Child

```text
Parent Component
       ↓
   @api Property
       ↓
Child Component
```

### Child → Parent

```text
Child Component
       ↓
  Custom Event
       ↓
Parent Component
```

---

# 🔄 Sprint 28 – Student Profile Form

## 📌 Business Requirement

Students should be able to view and update their profile information.

### Form Workflow

```text
👨‍🎓 Student
     ↓
👤 Profile Form
     ↓
✏️ Edit Information
     ↓
✅ Validate Fields
     ↓
💾 Save Changes
     ↓
🎉 Success / ⚠️ Error
     ↓
🔄 Refresh Data
```

The profile form should load existing values, allow editing, validate required fields, save changes, and communicate success or failure.

---

# ⚡ Lightning Data Service

## 📌 Business Requirement

Before writing custom Apex for standard record operations, the team should determine whether **Lightning Data Service (LDS)** can satisfy the requirement.

### Architecture Decision

```text
Requirement
     ↓
Can LDS handle it?
   ↙       ↘
 Yes        No
 ↓           ↓
LDS        Apex
```

LDS can provide standard mechanisms for retrieving and updating supported Salesforce records, reducing unnecessary custom server-side code.

---

# 🔄 Sprint 29 – Reactive Data & Refresh

## 📌 Business Requirement

When a student's information changes, dependent components should display the latest information.

For example, a change in **CGPA** can affect:

- 👤 Student Summary
- 💼 Eligible Jobs
- 📝 Application Eligibility

### Data Flow

```text
Student Profile
      ↓
Student Record Changes
      ↓
Student Summary Refresh
      ↓
Eligible Jobs Refresh
      ↓
Updated Student Experience
```

The system should avoid stale or contradictory information between components.

---

# 🔄 Sprint 30 – Reusable Components

## 📌 Business Requirement

Common UI behaviour should be implemented once and reused across multiple screens.

### Example

```text
ApplicationCard ──┐
                  ├── 🏷️ StatusBadge
InterviewCard ────┤
                  │
OfferCard ────────┘
```

A reusable component such as `StatusBadge` can accept:

- Status
- Variant
- Label

The PDF emphasizes **reusing meaningful behaviour rather than simply reusing markup**.

---

# 📭 Empty State Component

Instead of simply displaying:

```text
No records found.
```

A meaningful empty state can guide the user:

```text
📭 No Eligible Jobs

Check again when new opportunities
are added.

[ UPDATE PROFILE ]
```

The Empty State component can accept a title, message and optional action label.

---

# 📋 Business Requirements & Solutions

| Requirement                  | Solution                  |
| ---------------------------- | ------------------------- |
| Parent sends data to child   | ✅ `@api` Properties      |
| Child sends action to parent | 📡 Custom Events          |
| Update student profile       | 📝 LWC Form               |
| Basic record operations      | ⚡ Lightning Data Service |
| Validate user input          | 🔍 Client-side Validation |
| Protect business rules       | 🔐 Server-side Validation |
| Keep components synchronized | 🔄 Reactive Data          |
| Reuse common UI behaviour    | 🧩 Reusable Components    |
| Handle no data               | 📭 Empty State            |
| Handle processing            | ⏳ Loading State          |
| Handle failures              | ⚠️ Error State            |

---

# 💡 Why These Solutions?

## 📡 Why Custom Events?

Custom events allow child components to communicate user actions to their parent without directly modifying parent state.

---

## ⚡ Why Lightning Data Service?

LDS should be preferred when it can handle the required Salesforce record operation because it can reduce unnecessary custom Apex code.

---

## 🔐 Why Server-Side Validation?

Client-side validation improves user experience, but **server-side business validation must remain authoritative** so business rules cannot be bypassed.

---

## 🧩 Why Reusable Components?

Reusable components reduce duplication and provide consistent behaviour across multiple screens.

Examples:

- `StatusBadge`
- `JobCard`
- `EmptyState`
- `LoadingIndicator`

---

# ⚠️ Avoid "God Components"

A **God Component** tries to retrieve all data, own all state, handle every event and control every child.

### ❌ Poor Architecture

```text
StudentPortal
      ↓
    Everything
      ↓
     Apex
      ↓
    Everything
```

### ✅ Better Architecture

```text
StudentPortal
│
├── StudentSummary
├── StudentProfile
├── EligibleJobs
│   └── JobCard
└── MyApplications
    └── ApplicationCard
```

The parent coordinates while children maintain focused responsibilities.

---

# 📋 Key Engineering Principles

- ✅ Every component should have a clear responsibility.
- ✅ Use `@api` for parent-to-child communication.
- ✅ Use custom events for child-to-parent communication.
- ✅ Keep business rules on the server.
- ✅ Use LDS when it fits the requirement.
- ✅ Maintain clear data ownership.
- ✅ Refresh dependent components after data changes.
- ✅ Reuse meaningful components.
- ✅ Avoid unnecessary abstraction.
- ✅ Avoid "God Components".
- ✅ Design loading, success, empty and error states.
- ✅ Keep communication between components explicit.

---

# 🎯 Questions

## 1️⃣ How does a parent communicate with a child?

A parent passes information to a child through public properties exposed using `@api`.

---

## 2️⃣ How does a child communicate with a parent?

A child dispatches a **Custom Event**, which the parent listens for and handles.

---

## 3️⃣ What is the purpose of `@api`?

`@api` exposes a property or method so that a parent component can interact with a child component.

---

## 4️⃣ When should LDS be used instead of Apex?

LDS should be used when standard Salesforce record operations can satisfy the requirement without custom server-side logic.

---

## 5️⃣ What is reactive data?

Reactive data means dependent components can respond when underlying information changes and refresh the information they display.

---

## 6️⃣ What is a reusable component?

A reusable component provides a meaningful UI or business capability that can be used by multiple components or pages.

---

# 📈 Project Features

- ✅ Parent-Child Communication
- ✅ Custom Events
- ✅ `@api` Properties
- ✅ Student Profile Form
- ✅ Client-side Validation
- ✅ Server-side Validation
- ✅ Lightning Data Service
- ✅ Reactive Data
- ✅ Data Refresh
- ✅ Reusable Components
- ✅ Empty State
- ✅ Loading State
- ✅ Success & Error Handling
- ✅ Clean LWC Architecture

---

# 🎓 Learning Outcomes

Through this assignment, I learned how to:

- ⚡ Build multiple LWCs as one application
- 📡 Communicate between components
- 📝 Build and validate forms
- ⚡ Use Lightning Data Service
- 🔄 Manage reactive data
- 🧩 Build reusable components
- 📭 Create meaningful empty states
- ⚠️ Handle UI states professionally
- 🏗️ Avoid tightly coupled architectures
- 🧠 Design components with clear responsibilities

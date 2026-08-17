# 🔐 Salesforce Placement Management System

## 📅 Day 13 – Security Architecture & Access Control

### 📌 Project Overview

This sprint focused on implementing a **layered Salesforce security model** to control object access, record visibility, and field permissions using Roles, Permission Sets, Organization-Wide Defaults (OWD), Sharing Rules, and Field-Level Security.

---

## 🚀 Features Implemented

### 👥 Role-Based Security

- CEO → Placement Officer → Student hierarchy
- Record visibility using Role Hierarchy

### 🛡️ Permission Sets

- Student Permission Set
- Placement Officer Permission Set
- Integration User Permission Set

### 🔒 Record-Level Security

- Organization-Wide Defaults (OWD)
- Sharing Rules for Student records

### 📄 Field-Level Security

- Students can view application status only
- Placement Officers can update application status
- Integration fields secured

---

## 🏗️ Security Model

```text
CEO
│
└── Placement Officer
      │
      └── Student
```

---

## 🔑 Organization-Wide Defaults

| Object            | Access           |
| ----------------- | ---------------- |
| Student\_\_c      | Private          |
| Application\_\_c  | Private          |
| Job\_\_c          | Public Read Only |
| Offer_Letter\_\_c | Private          |

---

## ⚙️ Technologies Used

- Salesforce Security Model
- Roles & Role Hierarchy
- Permission Sets
- Organization-Wide Defaults
- Sharing Rules
- Field-Level Security

---

## ✅ Sprint Outcome

Implemented a secure, role-based access control system that protects student data while allowing Placement Officers to manage recruitment efficiently using Salesforce security best practices.

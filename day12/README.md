# 🚀 Salesforce Placement Management System

## 📅 Day 12 – Git, Salesforce CLI & Deployment

> This sprint focused on transforming the Placement Management System into a production-ready Salesforce project using Git, Salesforce CLI, Metadata, Sandboxes, and Deployment workflows.

## 📌 What I Implemented

- Git repository for source control
- Professional project structure
- Salesforce CLI authentication
- Retrieved Salesforce metadata
- Git commit & push workflow
- Deployment documentation
- Architecture & API documentation

## 🏗️ Project Structure

```text
placement-management-system/
│
├── README.md
├── force-app/
│   └── main/default/
│
├── docs/
│   ├── architecture/
│   ├── api/
│   └── deployment/
│
├── scripts/
└── .gitignore
```

This follows a professional Salesforce project repository structure.

## ⚙️ Git Workflow

```text
Working Files
      ↓
git add
      ↓
Staging
      ↓
git commit
      ↓
Local Repository
      ↓
git push
      ↓
GitHub
```

The workflow demonstrates how source code moves from local development to a remote GitHub repository.

## ☁️ Salesforce CLI

Commands practiced during the sprint:

```bash
sf org list
sf project retrieve start
sf project deploy start
git add .
git commit -m "message"
git push
```

Salesforce CLI enables repeatable authentication, metadata retrieval, deployment, and testing workflows.

## 📦 Metadata Retrieved

Retrieved metadata from the Developer Org:

- `Student__c`
- `Job__c`
- `Application__c`
- `Offer_Letter__c`
- Apex Classes
- Apex Triggers
- Lightning Web Components

### Metadata vs Business Data

Salesforce Metadata includes:

- Objects
- Fields
- Flows
- Apex Classes
- Apex Triggers
- Lightning Web Components

Business data includes actual Salesforce records such as:

- Student records
- Job records
- Application records
- Offer Letter records

## 🚀 Deployment Pipeline

```text
Developer
   ↓
Git Branch
   ↓
Code Review
   ↓
Testing
   ↓
QA
   ↓
UAT
   ↓
Production
```

A professional deployment follows:

```text
Build → Test → Validate → Deploy → Verify
```

## 🛠️ Key Concepts Learned

| Topic               | Status |
| ------------------- | ------ |
| Git & GitHub        | ✅     |
| Salesforce CLI      | ✅     |
| Metadata Retrieval  | ✅     |
| Git Branches        | ✅     |
| Pull Requests       | ✅     |
| Sandboxes           | ✅     |
| Scratch Orgs        | ✅     |
| Metadata API        | ✅     |
| Deployment Workflow | ✅     |

## ✅ Sprint Outcome

Successfully converted the Placement Management System into a **source-driven, version-controlled Salesforce application** with:

- GitHub integration
- Salesforce CLI workflow
- Metadata retrieval
- Deployment documentation
- Architecture documentation
- API documentation
- Professional repository structure

This sprint strengthened the project's **version control, deployment, documentation, and Salesforce development workflow**.

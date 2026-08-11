# 🚀 Day 11 – Crossing the Salesforce Boundary

## 📌 Project Overview

Day 11 focused on integrating the **Salesforce Placement Management System** with external systems using **REST APIs and Apex Callouts**.

The objective was to understand how Salesforce communicates securely with external applications and how to design reliable integrations using synchronous and asynchronous processing.

---

## 🎯 Key Concepts Learned

- 🔗 APIs and REST APIs
- 🌐 HTTP Methods – GET, POST, PUT, PATCH, DELETE
- 📦 JSON Request and Response Handling
- 🔄 Salesforce HTTP Callouts
- 🔐 Named Credentials
- 🔑 Authentication vs Authorisation
- 🔐 Auth Providers
- ⚡ Synchronous vs Asynchronous Integration
- ⏳ Queueable Apex for background callouts
- 🗓️ Scheduled Apex
- 📦 Batch Apex
- 🔁 Retry and Error Handling
- 🛡️ Idempotency and Duplicate Prevention
- 🌎 Salesforce Connect and External Objects
- 🔄 Point-to-Point vs Middleware Integration

---

# 🏗️ Engineering Sprint 32 – External Recruitment Integration

## 📌 Business Requirement

When a student's application is selected, Salesforce should automatically send the candidate information to an external recruitment platform.

### 🔄 Integration Flow

```text
Application Selected
        ↓
      Trigger
        ↓
     Service
        ↓
   Queueable Apex
        ↓
   Named Credential
        ↓
    REST API
        ↓
External Recruitment System
        ↓
 Candidate Information
```

### 📦 Information Sent

The integration sends information such as:

- Student Id
- Name
- Email
- Branch
- CGPA
- Job Id
- Company
- Role
- Selection Date

### 🛠️ Implementation

- Created Queueable Apex for external communication.
- Used HTTP Callouts to communicate with the external API.
- Used Named Credentials instead of hard-coded credentials.
- Processed the external API response.
- Stored the external candidate reference in Salesforce.

### ✅ Result

The selected application was successfully synchronized.

```text
Integration Status      : Sent
External Candidate Id  : Generated
Integration Error      : null
Queueable Status       : Completed
Number of Errors       : 0
```

---

# 🛡️ Engineering Sprint 33 – Integration Reliability Challenge

This sprint focused on making the integration reliable when the external system fails.

## 📊 Integration Tracking

The Application object tracks:

- Integration Status
- External Candidate Id
- Last Integration Attempt
- Integration Error

### 🔄 Integration Status Flow

```text
Selected
   ↓
Pending
   ↓
Queueable
   ↓
Success → Sent

Failure
   ↓
Retry Required
```

## ⚠️ Error Handling

The integration handles different API responses including:

- ✅ Success
- ❌ 400 – Bad Request
- 🔐 401 – Authentication Failure
- 🚫 403 – Forbidden
- 💥 500 – Server Error
- ⚠️ Unexpected Errors

### 🔥 Example Failure

The external service returned:

```text
HTTP 503 – Service Temporarily Unavailable
```

The application correctly recorded:

```text
Integration Status        : Failed
Integration Error         : External server error. HTTP 503
Last Integration Attempt  : Recorded
```

This demonstrates that Salesforce can track external integration failures instead of incorrectly marking a failed request as successful.

---

# 🏛️ Engineering Sprint 34 – Integration Architecture Challenge

Sprint 34 required designing three different integration scenarios.

## 1️⃣ Immediate Certification Verification

A student enters a certification number and Salesforce verifies it against an external service.

### 🏗️ Architecture

```text
LWC
 ↓
Apex
 ↓
External API
 ↓
Response
 ↓
LWC
```

### ❓ Why Synchronous?

The student needs the verification result immediately.

### ✅ Result

Certification verification was successfully implemented and tested.

```text
Certification Number : CERT-001

Success:
Certification verification completed.
```

---

## 2️⃣ Candidate Synchronisation

When a student is selected:

```text
Application Selected
        ↓
      Trigger
        ↓
   Queueable Apex
        ↓
    External API
```

### ❓ Why Asynchronous?

The user does not need to wait for the external recruitment system.

Queueable Apex allows the external communication to happen in the background.

---

## 3️⃣ Historical Synchronisation

For large-scale historical synchronization, the system uses scheduled processing.

### 🏗️ Architecture

```text
Scheduled Apex
      ↓
 Historical Sync
      ↓
   Batch Apex
      ↓
External Integration
      ↓
 Error Handling
      ↓
    Retry
```

A nightly scheduled job was configured for the historical synchronization process.

---

# 🔐 Security

Credentials and secrets should never be hard-coded inside Apex.

Instead, the integration uses:

```text
Apex
 ↓
Named Credential
 ↓
Authentication
 ↓
External API
```

This keeps authentication configuration separate from business logic and makes deployments safer.

---

# 🔄 Synchronous vs Asynchronous Integration

| Scenario                           | Approach             |
| ---------------------------------- | -------------------- |
| Certification verification         | ⚡ Synchronous       |
| Selected candidate synchronization | 🔄 Asynchronous      |
| Large historical synchronization   | 🗓️ Scheduled + Batch |

The decision is based on whether the user needs an immediate response and how much data needs to be processed.

---

# 🛡️ Reliability & Idempotency

External systems can become unavailable or return errors.

The integration therefore considers:

- API failures
- HTTP status codes
- Retry processing
- Integration status tracking
- External reference IDs
- Duplicate prevention
- Idempotency

The goal is to ensure that retrying an integration does not accidentally create duplicate candidate records.

---

# 📁 Project Evidence

The implementation was validated using:

- Salesforce Application records
- Salesforce UI
- Salesforce CLI SOQL queries
- Queueable Apex Job results
- Integration Status fields
- External Candidate ID
- Integration Error tracking
- Certification verification UI
- Scheduled Apex jobs

---

# 🧰 Technologies Used

- ☁️ Salesforce
- 💻 Apex
- ⚡ Lightning Web Components (LWC)
- 🔗 REST API
- 🔄 HTTP Callouts
- 📦 JSON
- ⏳ Queueable Apex
- 📦 Batch Apex
- 🗓️ Scheduled Apex
- 🔐 Named Credentials
- 🛠️ Salesforce CLI
- 🔍 SOQL

---

# ✅ Day 11 Outcome

Completed the integration layer of the Placement Management System.

### Completed

- ✅ External Recruitment Integration
- ✅ REST API Callouts
- ✅ Queueable-based Candidate Synchronization
- ✅ Named Credential Integration
- ✅ Integration Status Tracking
- ✅ Error Handling
- ✅ HTTP 503 Failure Handling
- ✅ Certification Verification
- ✅ Synchronous Integration
- ✅ Asynchronous Integration
- ✅ Scheduled Integration
- ✅ Batch Integration Architecture
- ✅ Retry and Idempotency Concepts
- ✅ Integration Architecture Design

---

# 🎯 Key Learning

A successful integration is not just about making an API call. It must also handle **authentication, failures, retries, duplicate requests, monitoring, and communication between independent systems**.

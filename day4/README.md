# 🚀 Salesforce Interview Readiness Bootcamp – Day 4

# 💻 Lightning Web Components (LWC)

> **Project:** Placement Management Portal  
> **Platform:** Salesforce Developer Edition  
> **Technology:** Lightning Web Components (LWC)

---

# 📖 Introduction

Day 4 focused on learning **Lightning Web Components (LWC)**, Salesforce's modern framework for building user interfaces.

In this hands-on session, I created my first Lightning Web Component, deployed it to a Lightning App Page, implemented data binding and event handling, and built a professional Placement Management Portal dashboard using HTML, JavaScript, CSS, and Static Resources.

---

# 🎯 Learning Objectives

✅ Understand Lightning Web Components (LWC)

✅ Learn LWC file structure

✅ Deploy components using Lightning App Builder

✅ Perform Data Binding

✅ Handle Button Click Events

✅ Build a Placement Dashboard

✅ Style components using CSS

✅ Use Static Resources

---

# 🛠 Technologies Used

| Technology                     | Purpose                 |
| ------------------------------ | ----------------------- |
| ☁ Salesforce Developer Edition | Development Platform    |
| ⚡ Lightning Web Components    | UI Development          |
| 🟧 HTML                        | Page Structure          |
| 🟨 JavaScript                  | Component Logic         |
| 🎨 CSS                         | Styling                 |
| 💻 VS Code                     | Development Environment |
| 🔧 Salesforce CLI              | Deployment              |

---

# 📂 LWC File Structure

```
placementHome
│
├── placementHome.html
├── placementHome.js
├── placementHome.css
└── placementHome.js-meta.xml
```

### 🟧 HTML

Responsible for:

- Page Layout
- Labels
- Buttons
- Images
- Dashboard UI

---

### 🟨 JavaScript

Responsible for:

- Variables
- Logic
- Event Handling
- Data Binding
- Updating Values

---

### 🎨 CSS

Responsible for:

- Styling
- Dashboard Layout
- Cards
- Colors
- Spacing

---

### ⚙ Meta XML

Responsible for:

- Component Visibility
- Lightning App Builder
- Deployment Targets

---

# 🧠 Part 1 – Think Before Coding

## ❓ 1. Why do users need a graphical interface?

A graphical interface allows users to interact with the application through buttons, forms, and dashboards instead of writing code or database queries.

---

## ❓ 2. Why can't users directly execute SOQL queries?

Users should not execute SOQL directly because it can expose sensitive data and bypass business logic. SOQL is executed securely through Apex.

---

## ❓ 3. Why is JavaScript required in LWC?

JavaScript controls the component's logic, stores variables, handles events, and updates the user interface dynamically.

---

## ❓ 4. What responsibilities belong to the UI?

- Display data
- Accept user input
- Show buttons
- Display forms
- Improve user experience

---

## ❓ 5. Which responsibilities should remain in Apex?

- Business Logic
- SOQL Queries
- DML Operations
- Database Access
- Validations

---

# 💻 Part 3 – Hands-on Activity 1

## ✅ Practical Work Completed

- Created a Lightning Web Component named **placementHome**
- Displayed **Welcome to Vishnu Placement Portal**
- Updated Meta XML configuration
- Deployed the component
- Added the component to a Lightning App Page
- Activated the page successfully

---

# 💻 Part 4 – Hands-on Activity 2

## ✅ Practical Work Completed

Created JavaScript variables:

- 👤 Student Name
- 🎓 Roll Number
- 🏫 Department

Displayed all variables in HTML using **Data Binding**.

Modified the values and verified that the UI updated automatically.

---

# 💻 Part 5 – Hands-on Activity 3

## ✅ Practical Work Completed

Created a button:

🔵 **Show Welcome Message**

When clicked, it displayed:

```
Welcome to Salesforce Development.
```

Implemented using JavaScript event handling.

---

# 💻 Part 6 – Hands-on Activity 4

## ✅ Practical Work Completed

Initially displayed

```
Status : Not Applied
```

Created an **Apply Now** button.

When clicked, JavaScript updated the status to

```
Status : Applied
```

No Apex or Database was used.

---

# 💻 Part 7 – Mini Project Enhancement

## ✅ Practical Work Completed

Built a Placement Management Portal Dashboard displaying:

📅 Today's Date

👋 Welcome Student

🏢 Number of Companies

💼 Number of Jobs

📄 Applications Submitted

### Additional Enhancements

- 🏫 Institute Logo
- 🎨 Professional Header
- 📊 Dashboard Cards
- 👤 Student Information Card
- 🎯 Responsive CSS Design
- ⚡ Lightning Icons

All values were hard-coded as required.

---

# 🔄 Part 8 – Understanding Data Binding

Example

```html
<p>Hello {studentName}</p>
```

When the value of `studentName` changes inside JavaScript, Lightning Web Components automatically updates the displayed value in the HTML.

### 📌 Explanation

Data Binding connects JavaScript variables with the HTML template, ensuring the UI stays synchronized with the component data.

---

# 🎤 Part 9 – Interview Questions

## 1️⃣ What is Lightning Web Components?

Lightning Web Components (LWC) is Salesforce's modern framework for building reusable, lightweight, and high-performance user interfaces using HTML, JavaScript, and CSS.

---

## 2️⃣ Why did Salesforce introduce LWC?

Salesforce introduced LWC to improve performance, follow modern web standards, simplify development, and create reusable UI components.

---

## 3️⃣ Difference between LWC and Aura

| Lightning Web Components  | Aura Components           |
| ------------------------- | ------------------------- |
| Faster                    | Comparatively Slower      |
| Uses Modern Web Standards | Uses Aura Framework       |
| Lightweight               | Higher Framework Overhead |
| Easy to Learn             | More Complex              |

---

## 4️⃣ What are the three files inside an LWC?

- 📄 HTML
- 🟨 JavaScript
- ⚙ Meta XML

_(CSS is optional but commonly used for styling.)_

---

## 5️⃣ Why is JavaScript required?

JavaScript is used for

- Variables
- Logic
- Event Handling
- Data Binding
- Updating UI

---

## 6️⃣ What is Data Binding?

Data Binding is the process of displaying JavaScript variables inside HTML using curly braces `{}`. Whenever a variable changes, the UI updates automatically.

---

## 7️⃣ Can LWC directly execute SOQL?

❌ No.

LWC cannot execute SOQL directly.

SOQL is executed through Apex Classes.

---

## 8️⃣ Why does LWC need Apex?

LWC uses Apex for:

- Reading Salesforce Records
- Updating Records
- Deleting Records
- Executing SOQL
- Business Logic

---

## 9️⃣ Where is the component deployed?

An LWC can be deployed on:

- 🏠 Home Page
- 📄 Record Page
- 📱 Lightning App Page

using Lightning App Builder.

---

## 🔟 Explain the component you built today.

I developed a Placement Management Portal using Lightning Web Components. The application displays student information, dashboard statistics, today's date, institute branding, and interactive buttons. JavaScript was used for event handling and data binding, CSS was used for styling, and a Static Resource was used to display the institute logo.

---

# 🎓 Learning Outcome

By completing this project, I gained practical experience in:

- ✅ Creating Lightning Web Components
- ✅ Understanding LWC Architecture
- ✅ HTML Templates
- ✅ JavaScript in LWC
- ✅ CSS Styling
- ✅ Data Binding
- ✅ Event Handling
- ✅ Lightning Buttons
- ✅ Static Resources
- ✅ Lightning App Builder
- ✅ Component Deployment

---

# 🏁 Conclusion

This project provided hands-on experience in developing modern Salesforce user interfaces using Lightning Web Components. It strengthened my understanding of component-based development, data binding, event handling, and UI design, preparing me for building dynamic Salesforce applications integrated with Apex in future modules.

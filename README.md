# SVGPTC No-Dues Clearance & Transfer Certificate Management Portal

## My Contribution — Faculty Dashboard & Department Dues Management

**Developer:** Khalid
**GitHub:** `khalid786-star`
**Role:** Faculty Dashboard & Department Dues Management Contributor
**Feature Branch:** `feat/khalid-faculty-module`
**Pull Request:** `#1`
**Commit:** `b48c870`

## 📌 Project Overview

The **SVGPTC No-Dues Clearance & Transfer Certificate Management Portal** is a web-based system designed to manage student no-dues clearance and Transfer Certificate workflows across different departments.

The system includes student, faculty, clerk, and administrative workflows for managing clearance requests, department dues, approvals, and completion status.

My contribution was focused specifically on the **Faculty Dashboard and Department Dues Management** area.

## 👨‍💻 My Work

I implemented a **Batch / Bulk Clearance Approval feature for Zero-Due Students** in the Faculty Dashboard.

The feature allows faculty members to select multiple eligible students and approve their department clearance together instead of approving each student individually.

### Main functionality I implemented

* Added checkbox-based student selection.
* Added select-all functionality for eligible students.
* Added bulk approval action.
* Added backend validation before approval.
* Prevented students with active dues from being batch approved.
* Enforced faculty department-level access.
* Prevented already-approved clearances from being processed again.
* Updated the overall no-dues request when all department clearances are approved.
* Added automated tests for the new functionality.
* Verified the existing single-student approval workflow still works.

## 🧑‍💻 Code I Worked On

### Backend

**`backend/src/controllers/facultyController.js`**

Implemented the batch clearance approval controller:

* Receives multiple student PINs.
* Validates the request.
* Checks faculty department scope.
* Checks active dues.
* Approves only eligible students.
* Updates approval information.
* Handles completion of the overall no-dues request.

**`backend/src/routes/facultyRoutes.js`**

Added the Faculty batch approval API route:

```text
POST /api/faculty/approve-batch
```

The route is protected by the existing faculty authentication middleware.

### Frontend

**`frontend/faculty.html`**

Added:

* Student selection checkboxes.
* Select-all checkbox.
* Batch approval action area.
* Batch approval button.

**`frontend/js/faculty.js`**

Implemented the frontend batch approval logic:

* Tracks selected students.
* Filters eligible zero-due students.
* Handles select/deselect operations.
* Sends selected student PINs to the backend.
* Displays success/warning messages.
* Refreshes the dashboard after approval.

### Automated Testing

**`backend/src/tests/facultyBatchApproval.test.js`**

Created automated tests covering:

1. Empty student PIN array validation.
2. Missing `student_pins` payload validation.
3. Active-due protection.
4. Successful approval of a clean student.
5. Multiple-student batch approval.
6. Department-level access control.
7. Existing single-student approval workflow.

**`backend/package.json`**

Updated the test script so the Faculty batch approval test suite can be executed through:

```text
npm test
```

## 🔐 Safety & Validation

The feature does not blindly approve every selected student.

Before approval, the backend verifies:

```text
Faculty Department
        ↓
Student Clearance
        ↓
Active Dues Check
        ↓
Already Approved Check
        ↓
Approve Clearance
```

Students with active dues are **not approved**.

Faculty members are also restricted to their own department's clearance records.

This keeps the bulk operation consistent with the existing department-level security model.

## 🧪 Testing

Automated testing result:

```text
7 tests
7 passed
0 failed
```

The tests verify both the new batch approval feature and important existing approval behavior.

I also performed manual verification through the Faculty Dashboard.

## 🔄 GitHub Development Workflow

I followed a real feature-development workflow:

```text
Feature Requirement
        ↓
Create Feature Branch
        ↓
Implement Backend
        ↓
Implement Frontend
        ↓
Add Automated Tests
        ↓
Run Tests
        ↓
Commit Changes
        ↓
Push Feature Branch
        ↓
Create Pull Request
        ↓
Code Review
```

### My branch

```text
feat/khalid-faculty-module
```

### My commit

```text
feat: add batch faculty clearance approval
```

### Commit

```text
b48c870
```

### Pull Request

```text
PR #1
feat: add batch faculty clearance approval
```

## 📸 Screenshots

Screenshots documenting my contribution will be added below.

### 1. Pull Request & Code Review

![image alt](https://github.com/khalid786-star/svgptc-faculty-contribution/blob/64a441b5f7f6bc5e93e1bf85efdc84ebf6609c00/01-pullrequest-and-review.png)

### 2. My Commit

![image alt](https://github.com/khalid786-star/svgptc-faculty-contribution/blob/4b326445d1de7971789af6298359de4e58b63c92/02-commit.png)

### 3. Faculty Dashboard Feature

![image alt](https://github.com/khalid786-star/svgptc-faculty-contribution/blob/0fb0c44ad73e3afa9bff238577e3664b32875f9d/03-faculty-feature.png%201.png)
![image alt](https://github.com/khalid786-star/svgptc-faculty-contribution/blob/f99148ad620d98933fc15d6454bc6a542e543cce/03-faculty-feature.png2.png)

### 4. Automated Test Results

![image alt]()

## 🛠️ Technologies Used

* HTML
* CSS
* JavaScript
* Node.js
* Express.js
* SQLite
* REST API
* Git
* GitHub
* Automated Testing

## 📚 What I Learned

Through this contribution, I gained practical experience with:

* Working inside an existing codebase.
* Understanding an existing backend/frontend architecture.
* Creating a feature without disturbing unrelated modules.
* Designing backend validation.
* Implementing department-level authorization.
* Connecting frontend actions to REST APIs.
* Writing automated tests.
* Using Git feature branches.
* Creating commits with meaningful messages.
* Pushing code to a remote repository.
* Creating and documenting a Pull Request.
* Participating in a team-style code review workflow.

## 🎯 My Role Summary

> **Khalid — Faculty Dashboard & Department Dues Management Contributor**

My work focused on improving the Faculty Dashboard by implementing **Batch / Bulk Clearance Approval for Zero-Due Students**, together with backend validation, department-level safety checks, frontend selection controls, and automated testing.

The contribution was developed on a dedicated feature branch and submitted through a Pull Request for team review.

## ⚠️ Contribution Note

This documentation describes **my individual contribution** to the team project.

I am not claiming ownership of the entire application. My contribution is specifically focused on the **Faculty Dashboard & Department Dues Management** functionality described above.

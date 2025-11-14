# Employee Management System

A modern Django-based Employee Management System designed to automate employee management, attendance tracking, leave workflows, payroll processing, and HR operations.
Built using Django REST Framework, JWT authentication, background tasks, and DOCX templating.

---

## Tech Stack

| Layer                       | Technology                          |
| --------------------------- | ----------------------------------- |
| **Language**          | Python 3                            |
| **Backend**           | Django, Django REST Framework (DRF) |
| **Database**          | SQLite                              |
| **API Documentation** | Swagger                             |
| **Background Jobs**   | Django Background Tasks             |
| **Document Export**   | docxtpl (DOCX Template Engine)      |
| **Authentication**    | Simple JWT (HTTP-only Cookies)      |

## Core Features

### Authentication & User Management

- Custom User Model with Custom User Manager
- Email + Password Authentication
- JWT Authentication (HTTP-only Cookie)
- Token Refresh Endpoint
- Email Verification using OTP
- Custom DRF Permissions
- Cookie-based Auth Class for DRF

### Department Managment

- Create & Manage Departments
- Automatic Department Creation on Migration (via Signals)

### Employee Management

- Employee Profile Management
- Payment Profile Tracking
- Signals automatically generate:
  - Leave balance
  - Payment profile
  - OTP on employee creation

### Attendance Management

- Mark Attendance (Check-in / Check-out)
- Automatic next-day Absent/Leave marking
- Automatic flagging of missing check-outs
- HR can update flagged attendance records

### Leave Management

- Leave Request Submission
- HR Leave Approval / Rejection
- Auto Leave Balance Initialization

### Payroll & Payslips

- Monthly Payroll Period Creation (auto-created on last day of month)
- Automatic & Manual Payroll Data Generation
- Payslip Generation in Background Task
- DOCX Payslip Export via Template (docxtpl)

---

## Additional System Features

- JSON-based Initial Configuration
- OTP auto-deletion (expired/used)
- Background job scheduling for:
  - Daily attendance fixes
  - Payroll cycle generation
  - Payslip processing

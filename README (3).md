# 🎓 Adaptive Learning Support Platform (ALSP)
### Java · JavaFX · Role-Based Access Control · Encryption · JUnit | ASU CSE 360

> **Objective:** A secure, role-based help system built for ASU's CSE 360 course, providing personalized assistance to Students, Instructors, and Admins through encrypted content, special access groups, and intelligent article management.

---

## 👥 Team Members
| Name | Role |
|------|------|
| Gayathri Kota | Functionality Testing & Final Document Review |
| Shaashvat Mittal | Testing & Final Document Review |
| Mukesh Tulluru | Functionality Testing & Final Document Review |
| Naga Sathvik Kommareddy | Functionality Testing & Final Document Review |
| Saisrivathsan Manikandan | Testing & Final Document Review |

---

## 📌 Project Overview

The ALSP is a desktop help system designed to support students, instructors, and admins in the CSE 360 course at ASU. It provides **customized, role-based assistance** so that students receive guidance suited to their skill level and specific needs — enhancing accessibility in a diverse learning environment.

The system was built across **4 development phases**, each adding new capabilities on top of the last. Every phase received a **perfect score with zero rework required.**

---

## 🗂️ Development Phases

### ✅ Phase 1 — Secure Identity Management & Role-Based Access Control

Established the core foundation of the system:

| Feature | Description |
|---------|-------------|
| **First Admin Setup** | First user to log in automatically becomes Admin |
| **Secure Account Creation** | All users (Admin, Student, Instructor) create accounts with username + password confirmation |
| **Account Setup Flow** | Post-login setup collects email, full name, and optional preferred name |
| **Role-Based Access** | 3 roles — Admin, Student, Instructor — each with unique home pages and permissions |
| **Multi-Role Selection** | Users with multiple roles choose which role to use per session |
| **Admin: Invite Users** | One-time invite codes for new user onboarding |
| **Admin: Reset Passwords** | Time-expiring one-time passwords for account recovery |
| **Admin: Delete Accounts** | Permanent deletion with confirmation dialog |
| **Admin: Manage Roles** | View, add, and remove roles for any user |

---

### ✅ Phase 2 — Data Management & Content Organization

Built on Phase 1 to add article management and content organization:

| Feature | Description |
|---------|-------------|
| **Unique Article IDs** | Each article gets a unique long integer ID — no duplicates |
| **Article Management** | Admins & Instructors can create, update, and delete help articles |
| **Backup & Restore** | Articles backed up to external files; restore with merge or replace options |
| **Article Grouping** | Articles organized into topic-based groups (e.g., Eclipse, GitHub) |
| **Keyword Search** | Students can search articles by keywords |
| **Role-Based Content Access** | Sensitive content restricted to appropriate roles |

---

### ✅ Phase 3 — Encryption, Special Access Groups & Enhanced Interfaces

Major security and usability upgrades:

| Feature | Description |
|---------|-------------|
| **Article Encryption** | Sensitive article bodies encrypted — secure even if memory is analyzed |
| **Special Access Groups** | Admins create/manage groups with encrypted content; access must be explicitly granted |
| **Group Admin Rights** | First instructor added to a group automatically gets admin rights for that group |
| **Student Interface** | Search by keyword, filter by content level (Beginner → Expert), send feedback |
| **Feedback System** | Students report missing or unclear articles; search queries tracked for new content |
| **Instructor Enhancements** | Manage special access groups, assign/revoke access rights, backup with encryption preserved |
| **JUnit Automated Testing** | Full test coverage for all non-UI components |
| **Enhanced Backup/Restore** | Backups include encrypted bodies; restores prevent data duplication |

---

### ✅ Phase 4 — Final Review & Verification

> Phase 4 focused on ensuring all requirements and previous grader feedback were fully implemented. Since the team received **no feedback from graders** and earned **full scores on all previous phases**, no changes were required.

---

## 🏗️ Architecture & Design

### System Roles

```
┌─────────────────────────────────────────────────────────┐
│                        ALSP System                       │
├───────────────┬──────────────────┬──────────────────────┤
│     Admin     │    Instructor    │       Student        │
├───────────────┼──────────────────┼──────────────────────┤
│ Manage users  │ Create articles  │ Search articles      │
│ Manage groups │ Manage groups    │ Filter by level      │
│ Encrypt data  │ Backup/Restore   │ Send feedback        │
│ Backup/Restore│ View articles    │ View articles        │
│ Manage OTPs   │ Assign access    │ Access by permission │
└───────────────┴──────────────────┴──────────────────────┘
```

### Core Classes

| Class | Responsibility |
|-------|---------------|
| `User` | Base class — stores username, password, email, name, roles, OTP |
| `Admin` | Extends User — full system management including encryption & special groups |
| `Instructor` | Extends User — article & group management, backup/restore |
| `Student` | Extends User — search, filter, feedback |
| `ArticleManager` | Add, update, delete, encrypt/decrypt articles |
| `GroupManager` | Create/delete groups, assign articles and users |
| `SpecialAccessGroupManager` | Manage restricted groups and their permissions |
| `EncryptionManager` | Encrypt and decrypt sensitive article content |
| `BackupHandler` | Secure backup and restore for articles and groups |
| `SearchManager` | Keyword search, filter by level or group |
| `UserList` | Add, remove, list users; assign to groups |
| `OTPList / OTP_Generator` | Generate and manage one-time passwords |

### UML & Flow Diagrams
- 📐 [UML Diagram (Miro)](https://miro.app/board/uXjVLXYd1CM=)
- 🔄 [Application Flow Diagram (Google Drive)](https://drive.google.com/file/d/1gLhN4WF_CvqZZOGD3xIURJZKMKYa9Ibt/view)

---

## 🧪 JUnit Testing

All non-UI components have automated test coverage using JUnit.

| Test Suite | What It Tests |
|------------|--------------|
| **Password Evaluator** | Uppercase, lowercase, numeric, special char, length requirements |
| **Search Testing** | Keyword search returns correct results |
| **OTP Generation** | One-time passwords generated and validated correctly |
| **Unique ID Generator** | IDs are unique across all articles |
| **Update DB** | Database updates persist correctly |
| **User List** | Add, remove, list users works as expected |
| **Article List** | Article management operations work correctly |

> ✅ All phases received **perfect scores** — zero rework across all 4 phases.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **Java** | Core application language |
| **JavaFX** | Desktop GUI framework |
| **JUnit** | Automated unit testing |
| **Encryption (AES)** | Secure article body storage |
| **GitHub** | Version control and collaboration |
| **Maven** | Build and dependency management |

---

## 🎬 Screencasts

| Phase | Type | Link |
|-------|------|------|
| Phase 1 | How-to-use | [Watch](https://asu.zoom.us/rec/share/dq8pqQ2kDyKLkAZBB6eNfZLEFbGt2Lk_DdLOiydhCzVJL4ZX8hXtbt.2elsIuIF1-84Wd) · Passcode: `Y!cYzZ&4rcHoCSU6A` |
| Phase 1 | Technical | [Watch](https://asu.zoom.us/rec/share/QZs_44qox1aPmxS7bIHasQAHRZI6Pp0JqzMVtx6u92a0jChHBS_F6EkBQFuflMvx.Lz-BjYptogfq0j-j) · Passcode: `P@Yj3#@h` |
| Phase 2 | How-to-use | [Watch](https://asu.zoom.us/rec/share/JSraHZi6K1Txr48iAWlB5N4y-onH3Iheo5fZmW4fAUu-FPkTzUdXE-YDfVplMx6m._fRKeds-VohpjoUH) · Passcode: `!EY7Qak$` |
| Phase 2 | Technical | [Watch](https://asu.zoom.us/rec/share/pVmnzfYEpf97NIyD1HU3SdiEgCsQdnglBFHPOAr9uIlFOUL-wqstQ6ywq1JRqQ9w.NoABAyHf9_utoq-z) |
| Phase 3 | How-to-use | [Watch](https://asu.zoom.us/rec/share/YKmsxwZ2DDBzEA8ommih5icxwUlBzcX8L65m3bOU_APXkiP2EHnPynF6V6JYshq_.vCIXCIGipvPY5nRa) · Passcode: `%pz1Hba0` |

---

## 🔗 Repository

**Team GitHub:** [shaashvat01/ASU-Help-System](https://github.com/shaashvat01/ASU-Help-System)

---

## 👩‍💻 Author

**Gayathri Kota**  
B.S. Data Science | Arizona State University  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-gayathrikota-blue?style=flat&logo=linkedin)](https://linkedin.com/in/gayathrikota)
[![GitHub](https://img.shields.io/badge/GitHub-gayathrikota-black?style=flat&logo=github)](https://github.com/gayathrikota)

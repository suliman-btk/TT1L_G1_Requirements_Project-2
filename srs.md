# 1. INTRODUCTION

## 1.1 Purpose

The purpose of this project is to develop a digital check-in and payment system for campus events that seamlessly integrates with the university’s student identification database and a secure payment gateway. The system aims to automate event attendance through student ID verification and ticket validation, reducing manual processes and human error.

Additionally, it enables secure on-site purchases—such as food, merchandise, and services—and equips event organizers with real-time analytics and reports to improve event management. Ultimately, the system enhances operational efficiency, security, and user experience for both students and staff.

## 1.2 Scope

The system allows students and vendors to check in to events via QR code, providing a streamlined and user-friendly experience. Key features include real-time notifications, integrated payment processing, and an event rating mechanism. The system does not include support for mapping, third-party navigation systems, or outdoor location services.

## 1.3 Product Overview

The digital check-in system is designed to manage campus event attendance and transactions efficiently. It enables students to check in using their university-issued IDs and supports both digital and physical ticket validation. The system interfaces with the university’s student database for real-time identity verification and with payment gateways for secure transactions.

Admin users can oversee events, monitor attendance, manage ticketing, and access comprehensive reports. The platform is intended for use by students, vendors, and administrators.

---
### 1.3.1 Product Perspective
The Campus Check-in System operates as a centralized event management platform that interacts with multiple user roles and external systems. The system interfaces with:

- **Students**, who can log in, register for events, view event details, and make payments.
- **Vendors**, who accept payments and view sales data.
- **Admins**, who manage events, monitor attendance, approve vendor access, and generate reports.
- **External systems**, including:
  - University student database for verification,
  - Online payment gateways for transaction processing,
  - Analytics modules for report generation.

This interaction is illustrated in **Figure 1**, which shows the high-level context of the system and its key data exchanges.

![Figure 1: System Context Diagram](./images/context_diagram.png)

### 1.3.2 Product Functions

| **Function**                     | **Description**                                                                                                                                         |
|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Student Check-in**            | Allows students to check in to events using their university ID cards or student numbers.                                                               |
| **Ticket Verification**         | Validates tickets during entry to ensure that only authorized participants are admitted.                                                               |
| **Payment Processing**          | Enables secure on-site purchases (e.g., food, merchandise) through integration with payment gateways.                                                  |
| **Real-time Attendance Tracking** | Records attendance as students check in and provides up-to-date data to the admin interface.                                                           |
| **Student Database Integration** | Connects to the university’s identification database for real-time verification of student status.                                                     |
| **Analytics and Reports**       | Generates post-event reports including attendance logs, transaction summaries, and ticket scan histories for students and vendors.                     |

*Table 1. Key product functions of the Campus Check-in System*

---

### 1.3.3 User Characteristics

| *Role*   | *Description*                                                                                 | *Required Knowledge*                                                                                       |
|-----------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| *Student* | University students using the system to check in and make purchases at events.                   | Basic familiarity with mobile or web-based applications.                                                     |
| *Admin*   | Staff responsible for managing events, tracking attendance, and accessing reports.               | Familiarity with admin dashboards, event management tools, and reporting interfaces.                         |
| *Vendor*  | On-site service providers (e.g., food or merchandise vendors) using the system to process transactions and monitor sales. | Basic understanding of digital payment platforms and ability to navigate the vendor interface. |

Table 2. User roles and required competencies
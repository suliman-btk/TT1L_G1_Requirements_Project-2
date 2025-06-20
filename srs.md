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

### 1.3.4 Limitations

- **Dependence on Internet Connectivity**: The system requires a stable internet connection for real-time check-ins, payment processing, and data synchronization.
- **Scalability Constraints**: Performance may degrade in large-scale events without proper server infrastructure.
- **Lack of Offline Support**: Version 1.0 does not support offline operations, including check-in and payment processing.
- **User Training Needs**: Admins and vendors may require minimal training to operate the system efficiently and avoid errors.
- **Device Compatibility**: Admins and vendors must use compatible tablets or laptops; inadequate hardware could hinder functionality.

---

### 1.4 Definitions

| **Term**             | **Definition**                                                                                          |
|----------------------|----------------------------------------------------------------------------------------------------------|
| **Integration**      | The process of linking the system with external platforms such as databases and payment gateways.        |
| **Analytics**        | Data analysis activities aimed at extracting insights, such as user activity or attendance patterns.      |
| **On-site Purchases**| Purchases made at the event location (e.g., food, merchandise).                                           |
| **Payment Gateway**  | A service that securely processes digital payments such as credit/debit card transactions.               |
| **Check-in System**  | A digital tool used to verify participant presence at events.                                             |
| **Ticket Verification** | The validation process that determines whether an event ticket is genuine and valid.                 |
| **End Users**        | Individuals interacting directly with the system (students, admins, vendors).                            |
| **Backend**          | The server-side logic and infrastructure that supports data processing, storage, and core functionality. |

*Table 3. Glossary of key terms*

## 3. Requirements

### 3.1 External Interfaces

This section defines the external interface requirements of the Campus Event Check-In System.  
It describes the user-facing actions and the corresponding inputs and outputs expected in each interaction. The interface elements are designed to offer a seamless and user-friendly experience, while ensuring secure and efficient communication with external components such as the university’s student database, integrated payment systems, and QR scanning tools. These interfaces serve as the connection point between users and the system’s core functionalities.

---

### 3.1.1 Login

Tables below define the interface components used in the login user interface.

#### `REQ_IO0001` - Login Button (Input)

| **Field**        | **Detail**                                                            |
|------------------|------------------------------------------------------------------------|
| **Version**      | 1.0                                                                    |
| **Item**         | Login Button (Input)                                                   |
| **Description**  | A button labeled “Login”                                               |
| **Purpose**      | Submits login credentials for authentication                          |
| **Input Format** | Button                                                                 |
| **Valid Input**  | Not Applicable                                                         |
| **Related I/O**  | REQ_IO00002, REQ_IO0003 (Both fields must be filled)                   |
| **Author**       | Suliman                                                                |

#### `REQ_IO0002` - Student ID Field (Input)

| **Field**        | **Detail**                                                 |
|------------------|-------------------------------------------------------------|
| **Version**      | 1.0                                                         |
| **Item**         | Student ID Field (Input)                                    |
| **Description**  | A text field labeled “Student ID”                           |
| **Purpose**      | Allows users to enter their Student ID                      |
| **Input Format** | String                                                      |
| **Valid Input**  | ASCII code from decimal 32 to 126                           |
| **Related I/O**  | None                                                        |
| **Author**       | Suliman                                                     |

#### `REQ_IO0003` - Password Field (Input)

| **Field**        | **Detail**                                                 |
|------------------|-------------------------------------------------------------|
| **Version**      | 1.0                                                         |
| **Item**         | Password Field (Input)                                      |
| **Description**  | A text field labeled “Password”                             |
| **Purpose**      | Allows users to enter their password                        |
| **Input Format** | String                                                      |
| **Valid Input**  | ASCII code from decimal 32 to 126                           |
| **Related I/O**  | None                                                        |
| **Author**       | Suliman                                                     |

#### `REQ_IO0004` - Failure Message (Output)

| **Field**        | **Detail**                                                 |
|------------------|-------------------------------------------------------------|
| **Version**      | 1.0                                                         |
| **Item**         | Failure Message (Output)                                    |
| **Description**  | Toast message for login failure                             |
| **Purpose**      | Notifies users of incorrect login                           |
| **Input Format** | Not Applicable                                              |
| **Valid Input**  | Not Applicable                                              |
| **Related I/O**  | REQ_IO0001 (Only displayed after submission)                |
| **Author**       | Suliman                                                     |

---

### 3.1.2 Event Registration

Tables below define the interface components used in the event registration user interface.

#### `REQ_IO0005` - Event List (Output)

| **Field**        | **Detail**                                                 |
|------------------|-------------------------------------------------------------|
| **Version**      | 1.0                                                         |
| **Item**         | Event List (Output)                                         |
| **Description**  | A list displaying available events with key details         |
| **Purpose**      | Allows students to browse and select events                 |
| **Input Format** | Not Applicable                                              |
| **Valid Input**  | Not Applicable                                              |
| **Related I/O**  | REQ_IO0006                                                  |
| **Author**       | Suliman                                                     |

#### `REQ_IO0006` - Register Button (Input)

| **Field**        | **Detail**                                                             |
|------------------|-------------------------------------------------------------------------|
| **Version**      | 1.0                                                                     |
| **Item**         | Button labeled “Register” next to each event                            |
| **Description**  | Initiates the registration process for a selected event                 |
| **Purpose**      | Button                                                                  |
| **Input Format** | Not Applicable                                                          |
| **Valid Input**  | Not Applicable                                                          |
| **Related I/O**  | REQ_IO0005, REQ_IO0007                                                  |
| **Author**       | Suliman                                                                 |

#### `REQ_IO0007` - Event Details Modal (Output)

| **Field**        | **Detail**                                                               |
|------------------|---------------------------------------------------------------------------|
| **Version**      | 1.0                                                                       |
| **Item**         | Event Details Modal (Output)                                              |
| **Description**  | A popup/modal showing full event information                              |
| **Purpose**      | Allows students to review event details before confirming                 |
| **Input Format** | Not Applicable                                                            |
| **Valid Input**  | Not Applicable                                                            |
| **Related I/O**  | REQ_IO0006, REQ_IO0008                                                    |
| **Author**       | Suliman                                                                   |

#### `REQ_IO0008` - Confirm Registration Button (Input)

| **Field**        | **Detail**                                                       |
|------------------|-------------------------------------------------------------------|
| **Version**      | 1.0                                                               |
| **Item**         | Confirm Registration Button (Input)                               |
| **Description**  | Button to finalize event registration                              |
| **Purpose**      | Submits event registration request                                 |
| **Input Format** | Button                                                             |
| **Valid Input**  | Not Applicable                                                     |
| **Related I/O**  | REQ_IO0007                                                         |
| **Author**       | Suliman                                                            |

#### `REQ_IO0009` - Registration Success Message (Output)

| **Field**        | **Detail**                                                               |
|------------------|---------------------------------------------------------------------------|
| **Version**      | 1.0                                                                       |
| **Item**         | Registration Success Message (Output)                                     |
| **Description**  | A confirmation message after successful registration                      |
| **Purpose**      | Informs student that registration is complete                             |
| **Input Format** | Not Applicable                                                            |
| **Valid Input**  | "Registration successful"                                                 |
| **Related I/O**  | REQ_IO0008                                                                |
| **Author**       | Suliman                                                                   |

#### `REQ_IO0010` - Registration Error Message (Output)

| **Field**        | **Detail**                                                                       |
|------------------|-----------------------------------------------------------------------------------|
| **Version**      | 1.0                                                                               |
| **Item**         | Registration Error Message (Output)                                               |
| **Description**  | A message displayed when registration fails                                       |
| **Purpose**      | Notifies student of issues with registration                                      |
| **Input Format** | Not Applicable                                                                    |
| **Valid Input**  | "Registration failed. Please try again."                                          |
| **Related I/O**  | REQ_IO0008                                                                        |
| **Author**       | Suliman                                                                           |

### 3.1.3 Event Check-in

Tables below define the interface components used in the event check-in user interface.

#### `REQ_IO0011` - QR Scanner Button (Input)

| **Field**        | **Detail**                                                             |
|------------------|-------------------------------------------------------------------------|
| **Version**      | 1.0                                                                     |
| **Item**         | QR Scanner Button (Input)                                               |
| **Description**  | A button that activates the device camera for QR scanning               |
| **Purpose**      | Allows student to initiate the check-in process by scanning a QR code   |
| **Input Format** | Button                                                                  |
| **Valid Input**  | Not Applicable                                                          |
| **Related I/O**  | REQ_IO0012                                                              |
| **Author**       | Suliman                                                                 |

#### `REQ_IO0012` - QR Code Data (Input)

| **Field**        | **Detail**                                                                  |
|------------------|------------------------------------------------------------------------------|
| **Version**      | 1.0                                                                          |
| **Item**         | QR Code Data (Input)                                                         |
| **Description**  | Encoded event-specific QR code content                                       |
| **Purpose**      | Provides event identity to validate check-in                                 |
| **Input Format** | String                                                                       |
| **Valid Input**  | Valid event token (UUID format or predefined code)                           |
| **Related I/O**  | REQ_IO0011                                                                   |
| **Author**       | Suliman                                                                      |

#### `REQ_IO0013` - Check-in Confirmation Message (Output)

| **Field**        | **Detail**                                                        |
|------------------|--------------------------------------------------------------------|
| **Version**      | 1.0                                                                |
| **Item**         | Check-in Confirmation Message (Output)                             |
| **Description**  | A success message upon successful check-in                         |
| **Purpose**      | Confirms successful attendance logging                             |
| **Input Format** | Not Applicable                                                     |
| **Valid Input**  | "Check-in successful"                                              |
| **Related I/O**  | REQ_IO0011                                                         |
| **Author**       | Suliman                                                            |

#### `REQ_IO0014` - Error Message (Output)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Error Message (Output)                                                      |
| **Description**  | A message displayed if QR is invalid or student not registered              |
| **Purpose**      | Informs user that check-in failed                                           |
| **Input Format** | Not Applicable                                                              |
| **Valid Input**  | "You are not registered for this event"                                     |
| **Related I/O**  | REQ_IO0011                                                                  |
| **Author**       | Suliman                                                                     |

### 3.1.4 Make Payment

Tables below define the interface components used in the make payment user interface.

#### `REQ_IO0015` - QR Scanner Button (Input)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | QR Scanner Button (Input)                                                   |
| **Description**  | A button to activate QR code scanner to identify the vendor                 |
| **Purpose**      | Initiates the process of identifying a vendor for payment                   |
| **Input Format** | Button                                                                      |
| **Valid Input**  | Not Applicable                                                              |
| **Related I/O**  | REQ_IO0016                                                                  |
| **Author**       | Lim Ai Nee                                                                  |

#### `REQ_IO0016` - Vendor QR Code (Input)

| **Field**        | **Detail**                                                                       |
|------------------|-----------------------------------------------------------------------------------|
| **Version**      | 1.0                                                                               |
| **Item**         | Vendor QR Code (Input)                                                            |
| **Description**  | Encoded vendor ID or payment session token                                        |
| **Purpose**      | Identifies which vendor the payment is intended for                               |
| **Input Format** | String                                                                            |
| **Valid Input**  | Valid vendor ID or session token                                                  |
| **Related I/O**  | REQ_IO0015                                                                        |
| **Author**       | Lim Ai Nee                                                                        |

#### `REQ_IO0017` - Amount Field (Input)

| **Field**        | **Detail**                                                                   |
|------------------|-------------------------------------------------------------------------------|
| **Version**      | 1.0                                                                           |
| **Item**         | Amount Field (Input)                                                          |
| **Description**  | A numeric text field for entering payment amount                              |
| **Purpose**      | Allows user to specify how much to pay the vendor                             |
| **Input Format** | Number                                                                        |
| **Valid Input**  | Positive decimal number (e.g., 1.00 to 999.99)                                 |
| **Related I/O**  | REQ_IO0018                                                                    |
| **Author**       | Lim Ai Nee                                                                    |

#### `REQ_IO0018` - Submit Payment Button (Input)

| **Field**        | **Detail**                                                           |
|------------------|-----------------------------------------------------------------------|
| **Version**      | 1.0                                                                   |
| **Item**         | Submit Payment Button (Input)                                         |
| **Description**  | A button to submit payment request                                    |
| **Purpose**      | Confirms and initiates the payment                                    |
| **Input Format** | Button                                                                |
| **Valid Input**  | Not Applicable                                                        |
| **Related I/O**  | REQ_IO0017                                                            |
| **Author**       | Lim Ai Nee                                                            |

#### `REQ_IO0019` - Payment Confirmation Message (Output)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Payment Confirmation Message (Output)                                       |
| **Description**  | A success message displayed after payment completion                        |
| **Purpose**      | Confirms that the payment has been processed                                |
| **Input Format** | Not Applicable                                                              |
| **Valid Input**  | "Payment successful"                                                        |
| **Related I/O**  | REQ_IO0018                                                                  |
| **Author**       | Lim Ai Nee                                                                  |

#### `REQ_IO0020` - Payment Error Message (Output)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Payment Error Message (Output)                                              |
| **Description**  | Message shown when payment fails                                            |
| **Purpose**      | Alerts user to retry or check their input                                   |
| **Input Format** | Not Applicable                                                              |
| **Valid Input**  | "Payment failed. Please try again."                                         |
| **Related I/O**  | REQ_IO0018                                                                  |
| **Author**       | Lim Ai Nee                                                                  |

---

### 3.1.5 Manage Events

Tables below define the interface components used in the manage events user interface.

#### `REQ_IO0021` - Event Table (Output)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Event Table (Output)                                                        |
| **Description**  | A table displaying all existing events with action buttons                  |
| **Purpose**      | Allows admins to view, edit, or delete existing events                      |
| **Input Format** | Not Applicable                                                              |
| **Valid Input**  | Not Applicable                                                              |
| **Related I/O**  | REQ_IO0022, REQ_IO0023, REQ_IO0024                                          |
| **Author**       | Lim Ai Nee                                                                  |

#### `REQ_IO0022` - Create Button (Input)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Create Button (Input)                                                       |
| **Description**  | A button labeled “Create Event”                                             |
| **Purpose**      | Opens a form/modal to create a new event                                    |
| **Input Format** | Button                                                                      |
| **Valid Input**  | Not Applicable                                                              |
| **Related I/O**  | REQ_IO0025 to REQ_IO0029                                                    |
| **Author**       | Lim Ai Nee                                                                  |

#### `REQ_IO0023` - Edit Button (Input)

| **Field**        | **Detail**                                                                   |
|------------------|-------------------------------------------------------------------------------|
| **Version**      | 1.0                                                                           |
| **Item**         | Edit Button (Input)                                                           |
| **Description**  | A button next to each event in the table to edit it                          |
| **Purpose**      | Opens the form pre-filled with event details for editing                      |
| **Input Format** | Button                                                                        |
| **Valid Input**  | Not Applicable                                                                |
| **Related I/O**  | REQ_IO0025 to REQ_IO0029                                                      |
| **Author**       | Lim Ai Nee                                                                    |

#### `REQ_IO0024` - Delete Button (Input)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Delete Button (Input)                                                       |
| **Description**  | A button next to each event for deletion                                    |
| **Purpose**      | Deletes the selected event after confirmation                               |
| **Input Format** | Button                                                                      |
| **Valid Input**  | Not Applicable                                                              |
| **Related I/O**  | None                                                                        |
| **Author**       | Lim Ai Nee                                                                  |

#### `REQ_IO0025` - Event Name Field (Input)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Event Name Field (Input)                                                    |
| **Description**  | Text field to enter the event name                                          |
| **Purpose**      | Specifies the name of the event                                             |
| **Input Format** | String                                                                      |
| **Valid Input**  | Alphabetic + alphanumeric string (3–50 characters)                          |
| **Related I/O**  | REQ_IO0022, REQ_IO0023                                                      |
| **Author**       | Lim Ai Nee                                                                  |

#### `REQ_IO0026` - Event Date Field (Input)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Event Date Field (Input)                                                    |
| **Description**  | Date picker for selecting the event date                                    |
| **Purpose**      | Specifies when the event will occur                                         |
| **Input Format** | Date                                                                        |
| **Valid Input**  | Any valid future date                                                       |
| **Related I/O**  | REQ_IO0022, REQ_IO0023                                                      |
| **Author**       | Lim Ai Nee                                                                  |

#### `REQ_IO0027` - Location Field (Input)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Location Field (Input)                                                      |
| **Description**  | Text field to enter the location of the event                               |
| **Purpose**      | Specifies the venue where the event will take place                         |
| **Input Format** | String                                                                      |
| **Valid Input**  | Free-text, max 100 characters                                               |
| **Related I/O**  | REQ_IO0022, REQ_IO0023                                                      |
| **Author**       | Lim Ai Nee                                                                  |

#### `REQ_IO0028` - Capacity Field (Input)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Capacity Field (Input)                                                      |
| **Description**  | Numeric field to define max number of attendees                             |
| **Purpose**      | Limits how many students can register                                       |
| **Input Format** | Integer                                                                     |
| **Valid Input**  | 1–1000                                                                      |
| **Related I/O**  | REQ_IO0022, REQ_IO0023                                                      |
| **Author**       | Lim Ai Nee                                                                  |

#### `REQ_IO0029` - Save/Update Button (Input)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Save/Update Button (Input)                                                  |
| **Description**  | A button to save or update event information                                |
| **Purpose**      | Commits the event changes to the system                                     |
| **Input Format** | Button                                                                      |
| **Valid Input**  | Not Applicable                                                              |
| **Related I/O**  | REQ_IO0025 to REQ_IO0028                                                    |
| **Author**       | Lim Ai Nee                                                                  |

### 3.1.6 Manage Attendance

Tables below define the interface components used in the manage attendance user interface.

#### `REQ_IO0030` - Event Dropdown (Input)

| **Field**        | **Detail**                                                         |
|------------------|---------------------------------------------------------------------|
| **Version**      | 1.0                                                                 |
| **Item**         | Event Dropdown (Input)                                              |
| **Description**  | Dropdown list of events for selection                               |
| **Purpose**      | Allows admin to select the event for attendance management          |
| **Input Format** | Dropdown                                                            |
| **Valid Input**  | Valid event names from system                                       |
| **Related I/O**  | REQ_IO0031, REQ_IO0032                                              |
| **Author**       | Azhar                                                               |

#### `REQ_IO0031` - Generate QR Button (Input)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Generate QR Button (Input)                                                  |
| **Description**  | A button to generate the event-specific check-in QR code                    |
| **Purpose**      | Enables the admin to display the QR code used by students to check in       |
| **Input Format** | Button                                                                      |
| **Valid Input**  | Not Applicable                                                              |
| **Related I/O**  | REQ_IO0030                                                                  |
| **Author**       | Azhar                                                                       |

#### `REQ_IO0032` - QR Code Image (Output)

| **Field**        | **Detail**                                                         |
|------------------|---------------------------------------------------------------------|
| **Version**      | 1.0                                                                 |
| **Item**         | QR Code Image (Output)                                              |
| **Description**  | QR code generated for check-in                                      |
| **Purpose**      | Displayed on the screen for scanning by students                    |
| **Input Format** | Image                                                               |
| **Valid Input**  | Auto-generated QR                                                   |
| **Related I/O**  | REQ_IO0031                                                          |
| **Author**       | Azhar                                                               |

#### `REQ_IO0033` - Attendance List Table (Output)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Attendance List Table (Output)                                              |
| **Description**  | Table listing all students who checked in                                   |
| **Purpose**      | Allows admin to view all registered attendees in real time                  |
| **Input Format** | Not Applicable                                                              |
| **Valid Input**  | Auto-fetched                                                                |
| **Related I/O**  | REQ_IO0030, REQ_IO0034                                                      |
| **Author**       | Azhar                                                                       |

#### `REQ_IO0034` - Refresh Button (Input)

| **Field**        | **Detail**                                                                       |
|------------------|-----------------------------------------------------------------------------------|
| **Version**      | 1.0                                                                               |
| **Item**         | Refresh Button (Input)                                                            |
| **Description**  | A button to reload the attendance list                                            |
| **Purpose**      | Refreshes the displayed attendance table to include latest check-ins              |
| **Input Format** | Button                                                                            |
| **Valid Input**  | Not Applicable                                                                    |
| **Related I/O**  | REQ_IO0033                                                                        |
| **Author**       | Azhar                                                                             |

---

### 3.1.7 Manage Payment

Tables below define the interface components used in the manage payment user interface.

#### `REQ_IO0035` - Payment Amount Field (Input)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Payment Amount Field (Input)                                                |
| **Description**  | Text field where vendor inputs the amount to be charged                     |
| **Purpose**      | Captures the transaction amount for a vendor sale                           |
| **Input Format** | Decimal Number                                                              |
| **Valid Input**  | Positive values (e.g., 1.00 – 999.99)                                        |
| **Related I/O**  | REQ_IO0036                                                                  |
| **Author**       | Azhar                                                                       |

#### `REQ_IO0036` - Confirm Payment Button (Input)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Confirm Payment Button (Input)                                              |
| **Description**  | Button to submit the entered payment                                        |
| **Purpose**      | Saves the transaction to the database                                       |
| **Input Format** | Button                                                                      |
| **Valid Input**  | Not Applicable                                                              |
| **Related I/O**  | REQ_IO0035                                                                  |
| **Author**       | Azhar                                                                       |

#### `REQ_IO0037` - Success Message (Output)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Success Message (Output)                                                    |
| **Description**  | Message confirming successful payment submission                            |
| **Purpose**      | Informs vendor that transaction was recorded                                |
| **Input Format** | Not Applicable                                                              |
| **Valid Input**  | "Payment recorded successfully"                                             |
| **Related I/O**  | REQ_IO0036                                                                  |
| **Author**       | Azhar                                                                       |

#### `REQ_IO0038` - Error Message (Output)

| **Field**        | **Detail**                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Version**      | 1.0                                                                         |
| **Item**         | Error Message (Output)                                                      |
| **Description**  | Message shown if input is missing or invalid                                |
| **Purpose**      | Warns vendor to enter a valid amount                                        |
| **Input Format** | Not Applicable                                                              |
| **Valid Input**  | "Please enter a valid amount"                                               |
| **Related I/O**  | REQ_IO0035                                                                  |
| **Author**       | Azhar                                                                       |


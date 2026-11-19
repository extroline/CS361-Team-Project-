# Tool Lending Library Functional Specification

**Team Members:** Dakota Rentz, Brendan Bessman, Zach Yarvis, Benny Garcia

## 1. Overview

The Tool Lending Library is a web-based application designed to support a new tool-lending service operated by the county library at a separate location. The system will allow eligible library patrons to browse available tools, manage reservations, track their borrowed items, and view and pay outstanding fees.

Patrons must be at least 18 years old, have their own valid county library card, register a new account, and complete an electronic liability waiver before borrowing tools. The system will use the county library's existing API to validate library cards and retrieve borrower metadata, while library employees will verify patron age using identification at checkout. Patrons may borrow up to five tools at a time, with an initial checkout period of up to two weeks and one optional renewal for the original checkout duration. Renewals are not permitted when another patron is on the tool's waitlist.

Library employees will use the system to verify borrower eligibility, process checkouts and returns, manage tool inventory, document maintenance issues, process in-person fee payments, and generate reports. Each physical tool will have a unique internal identifier and barcode for tracking purposes.

The system will also support tool waitlists, overdue fees, borrowing restrictions, and online payments. It will integrate with the county library's existing card-validation API while maintaining a separate website and inventory system for the Tool Lending Library. Patrons will have access to a personal dashboard displaying borrowing history, loan status, remaining days, reservations, and outstanding fees.

## 2. User Scenarios

### Scenario 1: Patron Registration

Sarah is a county library patron who wants to borrow tools for a home improvement project. She visits the Tool Lending Library website and creates an account using her valid county library card. The system verifies her card and retrieves borrower metadata through the county library's existing API. Sarah completes the electronic liability waiver and gains access to her personal dashboard, where she can view her borrowing history, loan status, remaining days, reservations, and outstanding fees.

### Scenario 2: Browsing and Reserving a Tool

Mike needs a power drill for a weekend project. He logs into the Tool Lending Library website and searches for available drills. After finding one, he reserves it through the website. The system places the drill on hold for three days and sends Mike a confirmation email with the pickup deadline. His reservation also appears on his dashboard.

### Scenario 3: Checking Out a Tool

David arrives at the Tool Lending Library to pick up a reserved circular saw. A library employee verifies his library card and confirms he is at least 18 years old by checking his identification. The employee scans the tool's barcode and processes the checkout. The system records the borrower, checkout date, and due date, and updates the tool's status to checked out. David can now view the borrowed tool and its return deadline on his dashboard.

### Scenario 4: Requesting a Renewal

Jessica has borrowed a pressure washer but needs additional time to finish her project. She logs into her dashboard and submits a renewal request. A library employee reviews the request through the administrative dashboard and confirms that Jessica has not previously renewed the tool and that no other patrons are on its waitlist. The employee approves the request, and the system extends the due date by the original checkout duration and notifies Jessica by email. If another patron is waiting, the renewal is denied.

### Scenario 5: Returning a Tool

James returns a borrowed electric sander to the Tool Lending Library. A library employee scans the tool's barcode and inspects its condition. After confirming the tool is in good working order, the employee completes the return in the system. The tool's status is updated, and James's borrowing record reflects the completed return.

### Scenario 6: Managing Overdue Tools

Emily forgets to return a borrowed ladder by its due date. The system sends her an email reminder on the due date and daily overdue reminders afterward. Once the due date passes, the system marks the tool as unreturned and displays its overdue status on Emily's dashboard along with any applicable fees. Late fees follow the library's established fee schedule and cap, including for unreturned tools. Emily can pay her outstanding fees online through her dashboard or visit the library to make a payment with an employee. The system records the payment and updates her outstanding balance. A library employee can also view the overdue checkout and payment status through the administrative dashboard.

### Scenario 7: Managing Tool Inventory

A library employee receives several new tools for the library. The employee logs into the administrative dashboard and adds each tool to the inventory with its name, category, unique identifier, and barcode. The employee can also update tool information, flag damaged tools for maintenance, and retire tools that are no longer suitable for lending. Tools currently checked out cannot be retired until they are returned.

### Scenario 8: Joining a Tool Waitlist

Alex wants to borrow a table saw, but all available units are currently checked out or reserved. He joins the waitlist through the website. When a tool becomes available for him, the system notifies Alex and provides a three-day pickup window. If Alex does not pick up the tool within that period, the system releases the hold and advances to the next eligible patron on the waitlist.

### Scenario 9: Generating Reports

A library employee wants to review the Tool Lending Library's borrowing activity and inventory status. The employee logs into the administrative dashboard and accesses the reporting section. The system generates reports showing currently checked-out tools, overdue tools, tools undergoing maintenance, and the most frequently borrowed tools. The employee uses this information to monitor inventory, identify overdue items, and evaluate tool demand.

### Scenario 10: Processing In-Person Fee Payments

Robert visits the Tool Lending Library to pay an outstanding overdue fee. A library employee accesses Robert's account through the administrative dashboard and reviews his outstanding balance. The employee processes or records Robert's payment, and the system updates his balance and saves the transaction in his payment history. Robert can view the updated balance through his personal dashboard.

## 3. Non-Goals

The following features are outside the scope of the Tool Lending Library application:

1. **Tool Delivery Services:** The system will not support shipping, home delivery, or off-site pickup. Patrons must visit the Tool Lending Library's physical location to pick up and return tools.

2. **Tool Sales and Purchasing:** The system will not support selling tools to patrons or purchasing replacement tools. It is intended for tool lending and inventory management only.

3. **Educational and Training Services:** The system will not provide tool-use classes, instructional videos, or certification courses.

4. **Native Mobile Applications:** The project will not include separate iOS or Android applications. Instead, the website will be mobile-friendly and accessible through web browsers.

5. **Multiple Library Locations:** The system will support one Tool Lending Library location and will not include multi-branch inventory management or tool transfers between locations.

6. **Self-Service Checkout:** Patrons will not be able to check out tools independently. All checkouts must be processed by authorized library employees.

7. **Separate Employee Permission Levels:** The system will not distinguish between different employee roles or administrative permission levels. All authorized library employees will have the same administrative access.

8. **Replacing the County Library's Existing System:** The Tool Lending Library will operate as a separate application and will not replace the county library's existing library management system. It will integrate with the existing library-card validation API.

9. **Dedicated Kiosk Application:** The system will not include a separate kiosk application. Patrons may access the Tool Lending Library website using library-provided computers or their own devices.

## 4. Use-Case Diagrams

The following diagrams illustrate the primary interactions between users and the Tool Lending Library system. The system has two user roles: Library Patrons and Library Employees. All library employees have the same administrative permissions.

### Library Patron Use-Case Diagram

This diagram shows the functions available to library patrons, including account registration, searching for tools, managing reservations and waitlists, viewing borrowing information, requesting renewals, and paying outstanding fees.

```mermaid

flowchart LR
    Patron["Library Patron"]

    subgraph System["Tool Lending Library System"]
        UC1(["Register / Log In"])
        UC2(["Browse / Search Tools"])
        UC3(["Reserve / Cancel Reservations"])
        UC4(["Join / Leave Waitlist"])
        UC5(["View Dashboard"])
        UC6(["Request Renewal"])
        UC7(["View / Pay Fees"])
    end

    Patron --- UC1
    Patron --- UC2
    Patron --- UC3
    Patron --- UC4
    Patron --- UC5
    Patron --- UC6
    Patron --- UC7
```
### Library Employee Use-Case Diagram

This diagram shows the administrative functions available to library employees, including verifying patron eligibility, processing checkouts and returns, approving renewals, managing inventory and reservations, tracking overdue tools, processing payments, and generating reports.

```mermaid

flowchart RL
    Employee["Library Employee"]

    subgraph System["Tool Lending Library System"]
        UC1(["Verify Patron Eligibility"])
        UC2(["Process Tool Checkouts"])
        UC3(["Process Returns / Inspections"])
        UC4(["Approve / Deny Renewals"])
        UC5(["Manage Tool Inventory"])
        UC6(["Manage Reservations / Waitlists"])
        UC7(["Track Overdue Tools / Fees"])
        UC8(["Process / Record Fee Payments"])
        UC9(["Generate Reports"])
    end

    Employee --- UC1
    Employee --- UC2
    Employee --- UC3
    Employee --- UC4
    Employee --- UC5
    Employee --- UC6
    Employee --- UC7
    Employee --- UC8
    Employee --- UC9
```
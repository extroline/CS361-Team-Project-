# Tool Lending Library Functional Specification

**Team Members:** Dakota Rentz, Brendan Bessman, Zach Yarvis, Benny Garcia

## 1. Overview

The Tool Lending Library is a web-based application designed to support a new tool-lending service operated by the county library at a separate location. The system will allow eligible library patrons to browse available tools, manage reservations, track their borrowed items and view outstanding fees.

Patrons must be at least 18 years old, have their own valid county library card, register a new account and complete an electronic liability waiver before borrowing tools. Patrons may borrow up to five tools at a time, with an initial checkout period of up to two weeks and one optional renewal for the original checkout duration.

Library employees will use the system to verify borrower eligibility, process checkouts and returns, manage tool inventory, document maintenance issues, and generate reports. Each physical tool will have a unique internal identifier and barcode for tracking purposes.

The system will also support tool waitlists, overdue fees, and borrowing restrictions. It will integrate with the county library's existing card-validation API while maintaining a separate website and inventory system for the Tool Lending Library.

## 2. User Scenarios

### Scenario 1: Patron Registration

Sarah is a county library patron who wants to borrow tools for a home improvement project. She visits the Tool Lending Library website and creates an account using her valid county library card. The system verifies her card through the county library's existing API. Sarah completes the electronic liability waiver and gains access to her personal dashboard, where she can manage her borrowing activity.

### Scenario 2: Browsing and Reserving a Tool

Mike needs a power drill for a weekend project. He logs into the Tool Lending Library website and searches for available drills. After finding one, he reserves it through the website. The system places the drill on hold for three days and sends Mike a confirmation email with the pickup deadline. His reservation also appears on his dashboard.

### Scenario 3: Checking Out a Tool

David arrives at the Tool Lending Library to pick up a reserved circular saw. A library employee verifies his eligibility, scans the tool's barcode, and processes the checkout. The system records the borrower, checkout date, and due date, and updates the tool's status to checked out. David can now view the borrowed tool and its return deadline on his dashboard.

### Scenario 4: Requesting a Renewal

Jessica has borrowed a pressure washer but needs additional time to finish her project. She logs into her dashboard and submits a renewal request. A library employee reviews the request through the administrative dashboard and approves it. The system extends the due date by the original checkout duration and notifies Jessica by email.

### Scenario 5: Returning a Tool

James returns a borrowed electric sander to the Tool Lending Library. A library employee scans the tool's barcode and inspects its condition. After confirming the tool is in good working order, the employee completes the return in the system. The tool's status is updated, and James's borrowing record reflects the completed return.

### Scenario 6: Managing Overdue Tools

Emily forgets to return a borrowed ladder by its due date. The system sends her an email reminder on the due date and daily overdue reminders afterward. Her dashboard displays the overdue tool and any applicable fees. A library employee can also view the overdue checkout through the administrative dashboard.

### Scenario 7: Managing Tool Inventory

A library employee receives several new tools for the library. The employee logs into the administrative dashboard and adds each tool to the inventory with its name, category, unique identifier, and barcode. The employee can also update tool information, flag damaged tools for maintenance, and retire tools that are no longer suitable for lending.

### Scenario 8: Joining a Tool Waitlist

Alex wants to borrow a table saw, but all available units are currently checked out or reserved. He joins the waitlist through the website. When a tool becomes available for him, the system notifies Alex and provides a three-day pickup window. If Alex does not pick up the tool within that period, the system releases the hold and advances to the next eligible patron on the waitlist.

### Scenario 9: Generating Reports

A library employee wants to review the Tool Lending Library's borrowing activity and inventory status. The employee logs into the administrative dashboard and accesses the reporting section. The system generates reports showing currently checked-out tools, overdue tools, tools undergoing maintenance, and the most frequently borrowed tools. The employee uses this information to monitor inventory, identify overdue items, and evaluate tool demand.
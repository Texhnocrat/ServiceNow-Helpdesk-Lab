🖥️ ServiceNow Help Desk Lab:

A hands-on ITSM lab completed in a ServiceNow Personal Developer Instance (PDI) simulating real help desk workflows. This project covers the full incident lifecycle, service request fulfillment, user administration, CMDB asset tracking, and reporting/dashboards.

______________________________________________________________________________________________________________________________________________________________________________________________________________________________



📋 Table of Contents:

Overview

Skills Demonstrated

Phase 1: Incident Management

Phase 2: Service Catalog & Request Fulfillment

Phase 3: User Administration & CMDB

Phase 4: Reporting & Dashboards

Key Concepts Learned

______________________________________________________________________________________________________________________________________________________________________________________________________________________________


Overview:

This lab was built to develop and demonstrate practical ServiceNow skills relevant to an IT help desk role. Every phase was completed manually inside a live PDI — no automation scripts, no shortcuts. Each step reflects a workflow a tier 1 or tier 2 help desk technician would perform daily.

___

Skills Demonstrated:

Incident creation, assignment, escalation, and resolution.

Service catalog navigation and request submission (end-user perspective).

Approval workflow processing and request fulfillment (admin perspective).

User account creation and role-based access assignment.

CMDB Configuration Item (CI) creation and asset tracking.

Linking CIs to incidents for repeat failure tracking.

Building visualizations and dashboards in Platform Analytics.

______________________________________________________________________________________________________________________________________________________________________________________________________________________________


Phase 1: Incident Management Lifecycle

What I did

Simulated the full lifecycle of a help desk incident — from initial creation through resolution and closure.

Step 1 — Created a new incident

Navigated to Incident → Create New and filled in all required fields:

Caller: Abel Schuehlein

Category: Software / Subcategory: Email

Impact: 2 – Medium / Urgency: 2 – Medium

Short description: "User unable to access Outlook after password reset"

Priority auto-calculated to 3 – Moderate based on Impact + Urgency values


*💡 Priority in ServiceNow is not manually set — it is calculated automatically from the Impact and Urgency fields using a priority lookup matrix. This ensures consistent prioritization across all technicians.*

******Show Image*****

Step 2 — Assigned and worked the incident

Assigned to group: Service Desk

Assigned to: myself (admin)

Changed State to: In Progress

Added a Work Note: "Contacted user, resetting Outlook profile. Monitoring."


*💡 Work Notes vs. Additional Comments: Work Notes are internal only — visible to agents but not the end user. Additional Comments are customer-visible. Knowing this distinction is critical in a real help desk environment to avoid accidentally sharing internal troubleshooting details with users.*

*Show Image*

Step 3 — Resolved and closed the incident

Changed State to: Resolved

Resolution Code: Solved (Permanently)

Resolution Notes: "Contacted user via phone. Confirmed issue began after password reset. Logged into user's workstation remotely, removed and re-added the Outlook profile under Control Panel > Mail. Entered new credentials and verified mailbox loaded successfully. User confirmed email access restored."

Added customer-facing comment: "Issue has been resolved. Please let us know if it recurs."

*Show Image*
*Show Image*

______________________________________________________________________________________________________________________________________________________________________________________________________________________________

Phase 2: Service Catalog & Request Fulfillment

What I did

Submitted a hardware request as an end user (impersonating Abel Schuehlein), then processed the approval and fulfilled the request as an admin.

*💡 REQ vs. RITM: When a user submits a catalog request, ServiceNow generates a REQ (Request) as the parent "shopping cart" record and one RITM (Requested Item) per line item ordered. A single REQ can contain multiple RITMs, each fulfilled by a different team. This separation is fundamental to how ServiceNow handles request fulfillment.*

Step 1 — Submitted the request as end user (Abel Schuehlein)

Navigated to Service Catalog → Hardware → Standard Laptop

Selected: Lenovo Carbon x1 ($1,100)

Checked: Adobe Acrobat (optional software)

Additional requirements: "Replacing aging Dell Latitude (4+ years old) with performance issues. Requesting Adobe Acrobat for PDF document management."

Submitted → Generated REQ0010001 and RITM0010001

*Show Image*
*Show Image*
*Show Image*

Step 2 — Approved and fulfilled the request as admin

Navigated to REQ0010001 → Approvers tab

Approved with comment: "Approved. Replacement laptop justified due to age and performance issues reported by user."

Opened RITM0010001, assigned to self, changed State to Work in Progress

Added Work Note: "Approval confirmed. Initiating laptop procurement and imaging process."

Changed State to Closed Complete

Added customer comment: "Your laptop request has been fulfilled. Your new Lenovo Carbon x1 will be delivered within 9 days."


*💡 Approval workflows depend on complete user records. During this lab I discovered that if a requester has no manager assigned in their user record, ServiceNow cannot trigger the approval workflow — the approval status remains "Not yet requested." In a production environment, complete and accurate user records are essential for all automated workflows to function correctly.*

*Show Image*
*Show Image*

______________________________________________________________________________________________________________________________________________________________________________________________________________________________

Phase 3: User Administration & CMDB

What I did

Created a new user account, assigned an ITSM role, created a computer asset in the CMDB, and linked it to an incident.

Step 1 — Created a new user

Navigated to User Administration → Users → New and created:

Name: Jason Bourne

User ID: jason.bourne

Title: IT Support Analyst

Department: IT

Manager: Abel Schuehlein

Then navigated to the Roles tab and assigned the itil role.

*💡 The itil role is the standard role assigned to help desk agents in ServiceNow. It grants access to create and manage incidents, problems, changes, and service requests — the core ITSM modules. Without this role, a user cannot interact with most help desk workflows.*

*Show Image*
*Show Image*

Step 2 — Created a CI in the CMDB

Navigated to Configuration → Computers → New and created:

Name: JASON-IBM

Manufacturer: Lenovo

Model ID: Lenovo ThinkStation S20

Serial number: L3BB911

Operating System: Windows XP Professional

Assigned to: Jason Bourne

Company: ACME North America

Then opened the CMDB Workspace to view the visual relationship map for the CI.

*💡 What is the CMDB? The Configuration Management Database (CMDB) is ServiceNow's inventory of all IT assets (called Configuration Items or CIs). Keeping the CMDB accurate is critical — it lets help desk teams know exactly what hardware and software exists, who it belongs to, and how assets relate to each other.*

*Show Image*
*Show Image*

Step 3 — Linked the CI to an incident

Opened INC from Phase 1, scrolled to the Affected CIs related list, and added JASON-IBM.

*💡 Why link CIs to incidents? If the same asset appears on multiple incidents over time, it signals a recurring hardware problem that may need replacement rather than repeated troubleshooting. This is how help desk teams identify chronic problem assets and escalate to Problem Management.*

*Show Image*

______________________________________________________________________________________________________________________________________________________________________________________________________________________________

Phase 4: Reporting & Dashboards

What I did

Built a visualization showing incidents grouped by category, then added it to a custom help desk dashboard alongside a live incident list.

*💡 Platform Analytics note: On this PDI (Xanadu release), the legacy Reports module has been replaced by Platform Analytics → Data Visualizations. The concepts are identical — the navigation path is different from older ServiceNow documentation.*

Step 1 — Created an incident visualization

Navigated to Platform Analytics → Create New Visualization

Table: Incident

Type: Bar Chart

Group by: Category

Stacked by: Created by

Saved as: "Incidents by Category — Lab"

*Show Image*

Step 2 — Built the Help Desk Lab Dashboard

Created a new dashboard: "Help Desk Lab Dashboard"

Added the bar chart visualization

Added a live incident list widget showing open incidents with Priority, State, Category, and Assignment Group columns

*Show Image*

______________________________________________________________________________________________________________________________________________________________________________________________________________________________

Key Concepts Learned:

Concept ................................................. What it means     

Priority matrix ...................................... Priority = Impact + Urgency, auto-calculated by ServiceNow

  Work Notes vs. Comments ............. Work Notes = internal only; Comments = visible to the end user

  REQ vs. RITM ........................................ REQ is the parent request; RITM is each individual line item

  itil role ..................................................... Standard help desk agent role granting access to core ITSM modules

  CI (Configuration Item) .................... Any IT asset tracked in the CMDB
  
  Affected CIs on incidents ................ Links assets to tickets for repeat failure tracking
  
  Approval workflows ............................ Triggered automatically based on the requester's manager field
  
  Platform Analytics ............................... ServiceNow's modern replacement for the legacy Reports module

  ____________________________________________________________________________________________________________________________________________________________________________________________________________________________


Lab completed March 2026 · ServiceNow PDI (Zurich release) · By Abel Schuehlein

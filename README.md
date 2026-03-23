<img width="1916" height="509" alt="Dashboard_Charts" src="https://github.com/user-attachments/assets/3fc6cb51-0efe-420e-b805-c20291dd6ac5" />

🖥️ ServiceNow Help Desk Lab:

A hands-on ITSM lab completed in a ServiceNow Personal Developer Instance (PDI) simulating real help desk workflows. This project covers the full incident lifecycle, service request fulfillment, user administration, CMDB asset tracking, and reporting/dashboards.

______________________________________________________________________________________________________________________________________________________________________________________________________________________________



📋 Table of Contents:

*Overview*

*Skills Demonstrated*

*Phase 1: Incident Management*

*Phase 2: Service Catalog & Request Fulfillment*

*Phase 3: User Administration & CMDB*

*Phase 4: Reporting & Dashboards*

*Key Concepts Learned*

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

<img width="578" height="594" alt="1 Incident_File_Navigation" src="https://github.com/user-attachments/assets/b496fbb5-8814-4eac-8285-82d21cef82d1" />
<img width="1919" height="592" alt="2 Incident_Table_Overview" src="https://github.com/user-attachments/assets/835a3e02-6fb7-45e7-ac67-a553751de4c5" />

Step 1 — Created a new incident

Navigated to Incident → Create New and filled in all required fields:

Caller: Melinda Carleton

Category: Software / Subcategory: Email

Impact: 2 – Medium / Urgency: 2 – Medium

Short description: "User unable to access Outlook after password reset"

Priority auto-calculated to 3 – Moderate based on Impact + Urgency values

<img width="1446" height="573" alt="3 INC_Form_Fill" src="https://github.com/user-attachments/assets/bcd3d16d-c693-40ec-9e54-13375ba7bee2" />



*💡 Priority in ServiceNow is not manually set — it is calculated automatically from the Impact and Urgency fields using a priority lookup matrix. This ensures consistent prioritization across all technicians.*


Step 2 — Assigned and worked the incident

Assigned to group: Service Desk

Assigned to: myself (admin)

Changed State to: In Progress

Added a Work Note: "Contacted user, resetting Outlook profile. Monitoring."


*💡 Work Notes vs. Additional Comments: Work Notes are internal only — visible to agents but not the end user. Additional Comments are customer-visible. Knowing this distinction is critical in a real help desk environment to avoid accidentally sharing internal troubleshooting details with users.*

<img width="1868" height="715" alt="4 Assignment_To_Groupp" src="https://github.com/user-attachments/assets/9ae4e8f5-4b7b-43f2-9bb1-d6ce8af7661e" />
<img width="1919" height="742" alt="5 Assign_Fields_Change" src="https://github.com/user-attachments/assets/712260fa-6b24-4031-9b5f-9478f4a2436e" />
<img width="1396" height="560" alt="6 Abel_POV" src="https://github.com/user-attachments/assets/d7fd82ad-49f2-4743-b2bf-1f4e1901bb0b" />
<img width="497" height="462" alt="9 Comment_Section" src="https://github.com/user-attachments/assets/1b861cb6-c990-4ebf-9eb5-6e986c1e3ee1" />


Step 3 — Resolved and closed the incident

Changed State to: Resolved

Resolution Code: Solved (Permanently)

Resolution Notes: "Contacted user via phone. Confirmed issue began after password reset. Logged into user's workstation remotely, removed and re-added the Outlook profile under Control Panel > Mail. Entered new credentials and verified mailbox loaded successfully. User confirmed email access restored."

Added customer-facing comment: "Issue has been resolved. Please let us know if it recurs."
<img width="1358" height="815" alt="7 Overview_Page" src="https://github.com/user-attachments/assets/6908c118-924c-4a47-96de-460934f7ff00" />
<img width="2430" height="846" alt="8 Record_View" src="https://github.com/user-attachments/assets/2e4bdb8c-a326-4fdb-b7c2-7f0aa347b8e4" />
<img width="1404" height="815" alt="10 Activity_Stream" src="https://github.com/user-attachments/assets/51ab91e6-b396-497d-92c3-d9d058a47b41" />
<img width="1401" height="759" alt="11 Ticket_Lifecycle" src="https://github.com/user-attachments/assets/b54ea9d3-cfc4-404c-ac31-30aafdfa08d6" />



______________________________________________________________________________________________________________________________________________________________________________________________________________________________

Phase 2: Service Catalog & Request Fulfillment

What I did

Submitted a hardware request as an end user (impersonating Abel Schuehlein), then processed the approval and fulfilled the request as an admin.

<img width="556" height="434" alt="1B Impersonate" src="https://github.com/user-attachments/assets/f5b256a1-f786-4bb0-98f4-5f2c76e9743c" />

*💡 REQ vs. RITM: When a user submits a catalog request, ServiceNow generates a REQ (Request) as the parent "shopping cart" record and one RITM (Requested Item) per line item ordered. A single REQ can contain multiple RITMs, each fulfilled by a different team. This separation is fundamental to how ServiceNow handles request fulfillment.*

<img width="570" height="581" alt="2B Service_Catalog_Navigation" src="https://github.com/user-attachments/assets/fd53d8c0-5139-4ca0-93f5-8c83089eda6d" />
<img width="1917" height="637" alt="3B Service_Catalog" src="https://github.com/user-attachments/assets/e522a7af-6706-4752-9fbf-9d971c4862f4" />
<img width="1916" height="896" alt="4B Hardware_Page" src="https://github.com/user-attachments/assets/4b5903db-02d1-46c7-8fa5-03e6822a7b1a" />



Step 1 — Submitted the request as end user (Abel Schuehlein)

Navigated to Service Catalog → Hardware → Standard Laptop

Selected: Lenovo Carbon x1 ($1,100)

Checked: Adobe Acrobat (optional software)

Additional requirements: "Replacing aging Dell Latitude (4+ years old) with performance issues. Requesting Adobe Acrobat for PDF document management."

Submitted → Generated REQ0010001 and RITM0010001

<img width="1919" height="718" alt="5B Order_Now" src="https://github.com/user-attachments/assets/d77e4129-d902-4aa7-b2f0-3e57bef69d17" />
<img width="1919" height="488" alt="6B Order_Submitted" src="https://github.com/user-attachments/assets/d726b490-aefd-46f7-9d58-20bf8ff71510" />
<img width="1918" height="792" alt="7B REQ_Record" src="https://github.com/user-attachments/assets/b74bb9e4-e24f-4aa0-9fa1-883e51701f2d" />


Step 2 — Approved and fulfilled the request as admin

Navigated to REQ0010001 → Approvers tab

Approved with comment: "Approved. Replacement laptop justified due to age and performance issues reported by user."

Opened RITM0010001, assigned to self, changed State to Work in Progress

Added Work Note: "Approval confirmed. Initiating laptop procurement and imaging process."

Changed State to Closed Complete

Added customer comment: "Your laptop request has been fulfilled. Your new Lenovo Carbon x1 will be delivered within 9 days."

<img width="662" height="624" alt="8B Eric_Navigation" src="https://github.com/user-attachments/assets/7ebb83b4-d64e-40c0-bd5d-15a1fa22eab9" />
<img width="1912" height="253" alt="9B Requests_Overview" src="https://github.com/user-attachments/assets/f50942b7-5c60-4cb3-bfc7-dde0030c1c08" />
<img width="1899" height="449" alt="10B Approval_Page" src="https://github.com/user-attachments/assets/c992be17-a1a9-4e86-a1af-3fe30f3c81cc" />
<img width="1917" height="480" alt="11B Comment" src="https://github.com/user-attachments/assets/b9a6a3d4-c721-46c3-b5bf-9427a0a41485" />
<img width="1870" height="557" alt="12B Optional_Approval" src="https://github.com/user-attachments/assets/67e92775-eede-40d5-87d1-dcb9a0a879b6" />
<img width="1840" height="567" alt="13B APPROVED" src="https://github.com/user-attachments/assets/3fc1cd64-19eb-4168-8178-402b9804de8e" />
<img width="1218" height="308" alt="14B Activity_Summary" src="https://github.com/user-attachments/assets/173fc97c-4d29-4288-aaad-a7f1ee9a3c98" />




*💡 Approval workflows depend on complete user records. During this lab I discovered that if a requester has no manager assigned in their user record, ServiceNow cannot trigger the approval workflow — the approval status remains "Not yet requested." In a production environment, complete and accurate user records are essential for all automated workflows to function correctly.*


______________________________________________________________________________________________________________________________________________________________________________________________________________________________

Phase 3: User Administration & CMDB

What I did

Created a new user account, assigned an ITSM role, created a computer asset in the CMDB, and linked it to an incident.
<img width="769" height="560" alt="1C User_Navigation" src="https://github.com/user-attachments/assets/243ace45-7bcf-427c-900c-d2228b2f3ba9" />
<img width="1910" height="609" alt="2C User_List" src="https://github.com/user-attachments/assets/3421af7a-1614-433e-9a26-2bc17b39b3ed" />
<img width="1916" height="557" alt="3C User_Form" src="https://github.com/user-attachments/assets/ee5c2d10-bcd2-4583-8577-f0a304e8d317" />
<img width="1915" height="491" alt="4C User_Form_Fill" src="https://github.com/user-attachments/assets/5edfe90a-8aa8-4985-9649-6de64ad35b04" />



Step 1 — Created a new user

Navigated to User Administration → Users → New and created:

Name: Jason Bourne

User ID: jason.bourne

Title: IT Support Analyst

Department: IT

Manager: Abel Schuehlein

Then navigated to the Roles tab and assigned the itil role.

<img width="1913" height="753" alt="8C Related_Group_Lists" src="https://github.com/user-attachments/assets/176b3ee2-d974-4676-9716-9ead5b89d12e" />
<img width="1913" height="730" alt="9C Add_RolesTo_Group" src="https://github.com/user-attachments/assets/5cef28ca-23e4-4f29-8bcb-94db3e01aa2c" />
<img width="1895" height="686" alt="10C Roles_Added_Related_Lists" src="https://github.com/user-attachments/assets/0f0f8f3b-5641-4e10-b8f9-7e4000c8b975" />
<img width="1902" height="686" alt="11C Slushbucket_Group" src="https://github.com/user-attachments/assets/bf8d548a-d36a-4aa2-ac51-26520c3be356" />
<img width="1669" height="655" alt="12C Role_Nesting" src="https://github.com/user-attachments/assets/6ace5e4f-0053-45d0-ac6a-400959c13d4c" />

*💡 The itil role is the standard role assigned to help desk agents in ServiceNow. It grants access to create and manage incidents, problems, changes, and service requests — the core ITSM modules. Without this role, a user cannot interact with most help desk workflows.*

<img width="776" height="592" alt="5C Groups_Navigation" src="https://github.com/user-attachments/assets/b76b48c8-0b57-4d6e-bb9a-815d0ee6cb6b" />
<img width="1916" height="630" alt="6C Groups_List_View" src="https://github.com/user-attachments/assets/85c91210-7809-4cda-a072-66c9e34e5dd0" />
<img width="1915" height="259" alt="7C New_Group" src="https://github.com/user-attachments/assets/be7418d5-c521-41d2-bf3d-8e01c1bc2b2c" />

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

<img width="632" height="577" alt="13C CMDB_Navigation" src="https://github.com/user-attachments/assets/01566287-45bc-4d9c-b690-e0db7d488813" />
<img width="1913" height="622" alt="14C Computer_Table" src="https://github.com/user-attachments/assets/bfbede36-d909-4668-9458-8de1e6fbc49d" />
<img width="945" height="493" alt="15C Invalid_Reference" src="https://github.com/user-attachments/assets/cfb0e210-92fd-4e95-bd23-1923bc2ac40e" />
<img width="828" height="237" alt="16C Add_Company" src="https://github.com/user-attachments/assets/39dc220c-85c2-43d4-9023-6f3a116e7c6b" />
<img width="952" height="273" alt="17C Invalid_Reference_Fix" src="https://github.com/user-attachments/assets/fe23e6d2-4b48-4199-96c9-421b9786ae63" />
<img width="1913" height="637" alt="18C Computer_Details" src="https://github.com/user-attachments/assets/1b4ce492-860d-4aa2-9be6-cd32dd659f4a" />
<img width="1913" height="899" alt="20C CI_View_Map" src="https://github.com/user-attachments/assets/de772399-07a9-4f60-8a61-c5f0c49e1c21" />

*💡 What is the CMDB? The Configuration Management Database (CMDB) is ServiceNow's inventory of all IT assets (called Configuration Items or CIs). Keeping the CMDB accurate is critical — it lets help desk teams know exactly what hardware and software exists, who it belongs to, and how assets relate to each other.*

<img width="1823" height="531" alt="19C CI_Related_Lists" src="https://github.com/user-attachments/assets/88d7350c-8393-48f1-b0bf-e65be96b039d" />


Step 3 — Linked the CI to an incident

Opened INC from Phase 1, scrolled to the Affected CIs related list, and added JASON-IBM.

<img width="1899" height="430" alt="21C New_INC" src="https://github.com/user-attachments/assets/bae82c97-eff7-4550-a4d7-4edb4741b6fd" />
<img width="1913" height="428" alt="22C Assign_INC" src="https://github.com/user-attachments/assets/aee98b4b-83ab-4eec-a0f7-9ad56d76f1e5" />
<img width="990" height="752" alt="23C Affected" src="https://github.com/user-attachments/assets/bb667ed8-106c-490c-8a47-06357c2cc7a9" />
<img width="1768" height="266" alt="24C Affected_CIs" src="https://github.com/user-attachments/assets/42475d4a-a6fd-4489-b4a8-f89d78f7e330" />

*💡 Why link CIs to incidents? If the same asset appears on multiple incidents over time, it signals a recurring hardware problem that may need replacement rather than repeated troubleshooting. This is how help desk teams identify chronic problem assets and escalate to Problem Management.*

______________________________________________________________________________________________________________________________________________________________________________________________________________________________

Phase 4: Reporting & Dashboards

What I did

Built a visualization showing incidents grouped by category, then added it to a custom help desk dashboard alongside a live incident list.

<img width="584" height="499" alt="1D Analytics_Menu_Search" src="https://github.com/user-attachments/assets/8811bf23-354c-4650-b30d-9422579a3b1b" />
<img width="1606" height="908" alt="2D Analytics_Center_Landing" src="https://github.com/user-attachments/assets/2f26629b-2d33-4dbf-ba15-9604374fdc0b" />


*💡 Platform Analytics note: On this PDI (Xanadu release), the legacy Reports module has been replaced by Platform Analytics → Data Visualizations. The concepts are identical — the navigation path is different from older ServiceNow documentation.*

<img width="1599" height="911" alt="3D Create_New_Visualization" src="https://github.com/user-attachments/assets/41d6ea0c-43ff-4508-b480-c91c78796fa6" />
<img width="1919" height="891" alt="4D Add_Data_Source_Designer" src="https://github.com/user-attachments/assets/6188343b-6f53-4eff-9e56-e9d4d078591d" />

Step 1 — Created an incident visualization

Navigated to Platform Analytics → Create New Visualization

Table: Incident

Type: Bar Chart

Group by: Category

Stacked by: Created by

Saved as: "Incidents by Category — Lab"

<img width="1601" height="861" alt="5D Select_Vertical_Bar_Chart" src="https://github.com/user-attachments/assets/f463ff12-c092-4f72-9656-24a542abe804" />
<img width="426" height="231" alt="6D Naming_Incident_Chart" src="https://github.com/user-attachments/assets/081407c1-c215-4629-8713-6957c9e5e2a0" />
<img width="1602" height="854" alt="7D Group_By_Category" src="https://github.com/user-attachments/assets/7a4a1553-0a54-4366-af85-0fe490410988" />
<img width="1216" height="830" alt="8D Stack_By_Created_By" src="https://github.com/user-attachments/assets/86e5660c-26ad-4a4e-b889-476a9cc4e2ab" />
<img width="762" height="269" alt="9D Add_Bookmark_Selection" src="https://github.com/user-attachments/assets/62e737c2-4b82-4317-ae47-4f6dcb655399" />
<img width="1906" height="839" alt="11D Library_Chart_Selection" src="https://github.com/user-attachments/assets/d1f07252-db53-4ec5-bbbe-705c5a8735cd" />


Step 2 — Built the Help Desk Lab Dashboard

Created a new dashboard: "Help Desk Lab Dashboard"

Added the bar chart visualization

Added a live incident list widget showing open incidents with Priority, State, Category, and Assignment Group columns

<img width="1918" height="850" alt="10D Dashboard_Add_Element" src="https://github.com/user-attachments/assets/dfac440b-f243-473b-8be0-412f37d9529b" />
<img width="1917" height="616" alt="12D Final_Help_Desk_Dashboard" src="https://github.com/user-attachments/assets/323d1bc9-6034-44c9-99ee-10e4251b6e2f" />



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

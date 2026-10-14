**Identity Governance & Administration (IGA)**

This project focuses on Identity Governance and Administration (IGA) using Microsoft Entra ID, demonstrating how to manage the employee identity lifecycle, including onboarding new employees, updating access permissions as they move between teams, and revoking access when they leave the organization.

**Part 1: Designing the Automated JML Lifecycle Workflow**

1. The Joiner (Onboarding): Provision new hires and contractors securely, grant appropriate role-based access, and enforce security policies from the outset without manual IT tickets.

•	Trigger Source: HR inputs the new employee’s basic details, employment type (employee vs. contractor), department, manager, and confirmed start date into Workday.

•	Action Taken: The Identity Provider provisions the employee's official identity, adds the employee to groups based on their roles, and enforces baseline security 

•	System of Record: Workday 


2. The Mover (Internal Transfer)
   
•	Trigger Source: HR updates the employee's department or role in Workday.

•	Action Taken: Identity provider re-evaluates the employee's permissions to fit the new role, eliminating permission creep as the employee transitions into the new role.

•	System of Record: Workday 


3. The Leaver (Offboarding)
   
•	Trigger Source: HR logs an effective termination date, contract expiration date, or immediate termination status in Workday.

•	Action Taken: An automated offboarding workflow executes an instant kill-switch. The user account status in the IdP is moved from "Active" to "Disabled/Blocked." All open sessions and logins are revoked across all platforms

•	System of Record: Workday 


**Part2: Access Certification & Audit Campaign**

An access audit was performed on 4 high-risk profiles to  identify compliance or security violations and decide whether to Certify (Keep), Modify (Restrict), or Revoke (Terminate) access.

<img width="1081" height="651" alt="Screenshot 2026-10-13 220257" src="https://github.com/user-attachments/assets/e25cfb91-20ee-44b4-99e0-7b76cb3a5b1d" />




<img width="1054" height="546" alt="Screenshot 2026-10-13 220312" src="https://github.com/user-attachments/assets/a289d190-eb36-4d56-ab1a-22291ed6b5b9" />



**Part 3: Identity Governance Hands-on using Entra ID**
The hands-on lab implements identity governance administration by  building a group-based lifecycle structure, provisioning a test contractor, assigning group-based permissions, and executing an instant offboarding kill switch.


**Step 1** created a security group in Entra ID named **SG-Temporary-Contractors**.

<img width="1134" height="736" alt="Screenshot 2026-10-13 202945" src="https://github.com/user-attachments/assets/69740d0e-d551-40a8-9dba-6cb44c3d2c8c" />

 
**Step 2** Created a user  **contractor.test ** and added the contractor to the previously created group


<img width="1350" height="721" alt="Screenshot 2026-10-13 203222" src="https://github.com/user-attachments/assets/e9a25911-430a-41db-8218-bb5b19866192" />



<img width="1350" height="721" alt="Screenshot 2026-10-13 203222" src="https://github.com/user-attachments/assets/0fe71cb1-6135-4ad3-8d26-a975e20b831b" />


**Step 3** Created a Group-Based Resource Access (Salesforce app)

<img width="1023" height="669" alt="Screenshot 2026-10-13 204901" src="https://github.com/user-attachments/assets/0c624233-a629-4ea5-b93e-7f3d12efa8c3" />



**Step 4:** Executing the Instant Offboarding (The Leaver / Kill-Switch). The contractor's login was disabled 

<img width="1322" height="739" alt="Screenshot 2026-10-13 211458" src="https://github.com/user-attachments/assets/8f4060e4-2c2b-4831-8f82-647a962e9654" />













